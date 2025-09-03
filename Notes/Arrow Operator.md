---
alias: [->]
subject: Computer Science 2
tags: [undergrad]
---
# Arrow Operator


> [!note]
> Used to access object members through a pointer to an object.

> [!example]
> ```cpp
> class genZ {
> 	public:
> 		genZ();
> 		void originalJoke(string j);
> 		string humor();
> 	private:
> 		string jokes[10];
> }
> 
> int main() {
> 	genZ kevin();
> 	kevin.originalJoke("Stonks");
> 	genZ *kevin_ptr = &kevin;
> 	(*(kevin_ptr)).humor(); || kevin_ptr -> humor(); // equivalent operations
> 	return 0;
> }

## References
1. [[Pointer]]
2. [[Derefence Operator]]
3. [[Object]]