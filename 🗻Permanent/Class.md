---
alias: []
subject: Computer Science 2
tags: [school]
---
# Class

> [!note]
> Are used to create complex data types. Variables of class types are called objects.

````ad-example
```cpp
// student.h
class student {
	public:
		void set_values(int, int); //Method
		int area();

	private:
		int width; //Field
		int height;
}

// student.cpp
#include "student.h"

void student::set_values(int a, int b) {
	this -> width = a;
	this -> height = b;
}

int student::area() {
	return width * height;
}
````

## References
1. [[C++ Compound Types]]