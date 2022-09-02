---
alias: [*]
subject: Computer Science 2
tags: [school]
---
# Derefence Operator


> [!note]
> Returns the value a memory address is pointing to.

````ad-example
```cpp
#include <iostream>
using namespace std;

int main() {
	int x = 5;
	cout << &x << endl; // print out the memory address of x
	cout << *(&x) << endl; // print out the value x's memory address is referring to
	return 0;
}
````

## References
1. [[Memory Allocation]]