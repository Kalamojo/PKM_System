---
aliases:
  - \&
subject: Computer Science 2
tags:
  - undergrad
---
# Address-of Operator

> [!note]
> When paired with a variable, returns the memory address of said variable.

> [!example]
> ```cpp
> #include<iostream>
> using namespace std;
> 
> int main() {
> 	int x = 5;
> 	cout << x << endl; //print out the value of x
> 	cout << &x << endl; // print out the memory address of x
> 	return 0;
> }

## References
1. [[Memory Allocation]]