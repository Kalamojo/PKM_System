---
alias: []
subject: Computer Science 2
tags: [undergrad]
---
# Dot Operator

> [!note]
>Used to access the members of an object, like the functions in a class.

> [!example]
> ```cpp
> class M1 {
> 	public:
> 		int num;
> 		void set_x(int s);
> 		int get_x();
> 	private:
> 		int x;
> }
> 
> int main() {
> 	M1 course;
> 	course.num = 5;
> 	course.set_x(3);
> 	cout << course.num << course.get_x();
> 	return 0;
> }

## References
1. [[Object]]