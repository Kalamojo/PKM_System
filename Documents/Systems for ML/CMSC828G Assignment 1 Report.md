# Report 1

## All-Gather Algorithm

I decided to implement ring and recursive versions of the all-gather algorithm. As we are all familiar, its purpose is to concatenate the buffers from each process, and store the concatenated result in each process as well.

![[Pasted image 20260221200947.png]]

### Ring

For the ring variant of the algorithm, the core technique is fairly straightforward. First, before any looping, I sent the buffer of each process to itself. This result is then received within the main program loop, which follows this high-level process:

```py
for round in range( number of processes ):
	data = receive_data( from process i-1 )
	output buffer = data
	send_data( data, to process i+1 )
```

And then finally, after the completion of the loop, the final set of buffers are received and stored. Each process is correctly sending and storing their data in the *next* process, in a ring-like fashion.

### Recursive

For the recursive variant of all-gather, things were a little more tricky. Rather than always sending one block of data to the next process, and always receiving one block from the previous process, sources and destinations grow exponentially further away in each round of the algorithm. Furthermore, the size of the data that is sent also grows at a similar rate.

![[Pasted image 20260221202140.png]]

The key challenge in designing this function was determining how to track both destinations and sources, based purely on the current process rank and round number. Fortunately, destinations and sources actually turn out to be identical in this problem. When process 0 sends its data to process 1, process 1 is guaranteed to send its data to process 0 as well. The same pattern follows for the other processes, as pairs are formed for data transferal. Here is the high level depiction of the algorithm:

```py
source = current process
send_data( input buffer, to source )

for round in range( log_2 (number of processes) ): # because data sent is doubling
	data = receive_data( from source )
	output buffer = data
	
	sending_up, offset = check_if_send_up( current process, round )
	if sending_up:
		destination = current process - offset
	else:
		destination = current process + offset
	
	send_data( current output buffer, to destination )
	source = destination

data = receive_data( from source )
output buffer = data
```

To actually check if a current process is sending its data "up" (backwards in terms of process numbers) or "down" (forwards), I made use of the modulo function. Essentially, in the first (technically second) round of transfer, only even number processes send their data down, so I can simply do a check for $(\text{rank} \% 2) / 1$ . In the second round, however, it's not only the even processes, but every first 2 processes for every group of 4. In this case, we can do a check for $floor((\text{rank} \% 4) / 2)$. As you can see, the modulo operand, as well as the divisor, will simply double for each round, so tracking this result is easy enough. A similar process is used to calculate how far down the process needs to send its data, as well as how much data it needs to send.

## Results

To measure the performance of each process, and therefore algorithm, I made use of the all-reduce collective method. I added an `MPI.Wtime()` call at the beginning of the program, as well as another at the end, and found the difference between those times to get the process duration. From there, I used three different operations with all-reduce: min, max, and sum (divided by number of processes after).

### Summary

Perhaps the most surprising thing about the results was the extremely varied nature of them. In some of the smaller process counts, such as 16 and 32, there was not a significant difference between the average durations of the ring and recursive algorithms, for the both the 2 MiB and 4MiB message sizes. Furthermore, the magnitudes of these durations did not follow an obvious progression in all cases. For 64 processes, the average ring algorithm duration for 2 MiB messages was about 0.16 seconds, while it was 0.19 for 32 processes, completely contrary to my expectations.

The biggest differences between the ring and recursive algorithms occurred in the largest process size, 256. Here, the recursive algorithm actually performed worse, with average durations of 3.95 and 7.97 for 2 MiB and 4 MiB messages respectively, compared to the durations of 2.15 and 3.70 for the ring algorithm. However, due to the aforementioned variance in results, the minimum durations for the recursive algorithm were actually lower than that of the ring algorithm. This leads me to believe that while external factors may be at play here, such as the availability of resources, resulting in occasional suboptimal results. Conceptually, the recursive algorithm should be performing much better due to its reduced number of rounds, but perhaps operations of sending and receiving larger sizes of data at once tanked performance to a certain degree. Issues may also have arisen in the specific way I accessed the storage buffer for receive calls. Seeing that python array.array's implemented a `__buffer__` method, and therefore `recvbuf` as well, I utilized the `memoryview` python function to actually access slices of the buffer for storage. However, I didn't have much of a reference for doing this, and its possible that this method of access, especially in cases where larger slices of the array are accessed (such as in the recursive algorithm), may be causing extra overhead and extended process durations.

### Investigations

The biggest thing I wish to investigate is the optimal placing of `Wait` calls, for both send and receive requests. Originally, I tried abstaining from using any waits for `Isend` calls. However, interestingly enough, this resulted in issues with only the ring algorithm. Currently, my `Wait`'s for send requests are called right after receiving previous data, but perhaps these should be delayed right up until another send call is about to be made. Or perhaps they should simply be stored, and awaited at the end of the program sometime. I'm hoping that I'll gain a better intuition for this as I learn more in the course.