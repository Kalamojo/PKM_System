---
alias: []
subject: Computer Science 2
tags: [school]
---
# Constructor

> [!note]

> [!info]
> The name of the constructor matches the name of the class.

````ad-example
```cpp
//Rectangle.h
class Rectangle {
	public:
		Rectangle(int, int); //Constructor
		void setValues(int, int);
		int area();

	private:
		int width;
		int height;
}

//Rectangle.cpp
#include "Rectangle.h"
Rectangle::Rectangle(int w, int h) {
	this -> width = w;
	this -> height = h;
}
````

## References
1. [[Class]]