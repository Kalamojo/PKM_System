---
alias: [new]
subject: Computer Science 2
tags: [school]
---
# 'New' Operator

> [!note]
> Can be used to allocate a single variable/object or an array of variables/objects Returns a pointer to the data type allocated. Is used to dynamically allocate memory.

````ad-example
```cpp
char *char_ptr = new char;
int *int_array = new int[20]; 
MyClass *m1 = new MyClass(1,1,2); // class constructor
````

## References
1. [[Pointer]]
2. [[Memory Allocation]]
3. [[Dynamic Memory Allocation]]