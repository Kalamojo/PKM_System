---
alias: []
subject: Computer Science 2
tags: [school]
---
# Recursive Function


```ad-note
A function that makes a call to itself. An alternative method to linear functions, 
```

````ad-example
 
```cpp
int fibba(int n) {
	if(n <= 0) {
		return 0;
	}
	else if(n == 1) {
		return 1;
	}
	else {
		return fibba(n-1) + fibba(n-2);
	}
}
````

## References
1. [[Recursion]]
2. [[Function]]