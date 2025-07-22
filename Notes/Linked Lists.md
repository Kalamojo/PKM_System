---
alias: ["Linked List"]
tags: [personal]
---
# Linked Lists

> [!note]
> Linked lists are data linked together by pointers.

> [!info]
> Unlike arrays, you can't use an index to access specific items. Also unlike arrays, they don't require a defined size.

Linked lists are made up of **nodes**. These nodes are just things that have some *data* attribute and *next* attribute.

````ad-example
Concept:
![[Linked Lists 2022-10-11 15.48.33.excalidraw|center|300]]

Code:
```cpp
node* a = new node(3);
````

Whenever nodes are linked together, they form a linked list.

````ad-example
Concept:
![[Linked Lists 2022-10-11 15.53.17.excalidraw|center]]

Code:
```cpp
node* a = new node(3);
node* b = new node(7);
a->next = b;
````

````ad-example
Printing out a Linked List:
```cpp
while (temp != nullptr) {  // While the current node is not null
	cout << temp->data << endl; // Print out the value of the node
	temp = temp->next; // Current node is now pointing to the next
}
````

````ad-example
Searching a linked list for a value:
```cpp
while (temp != nullptr) {  // While the current node is not null
	if (temp->data == value) { // check if node has the search value
		return true;
	} else {
		temp = temp->next; // Current node is now pointing to the next
	}
}
return false;
````

````ad-tip
Linked lists don't allow you to access items by index, and you would have to traverse the list to get a certain item. However, you can assign temporary pointers to nodes to make accessing them easier.
```cpp
node* head = new node(1); // create a head node
head->next = new node(2); // point head to a second node
head->next->next = new node(3); // third node
head->next->next->next = new node(4); // fourth node

node* temp = head->next->next->next; // assign a temp pointer to fourth node
````

```ad-summary
Linked lists are like arrays in the sense that they are things that hold multiple items. However, they two are very different.
While arrays are like these big containters that you place items in, linked lists are more like independant items connected only by links. Both data structures have their uses in specific situations, but learning each will prepare you better for solving problems in the future.
```
