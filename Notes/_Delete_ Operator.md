---
alias: [Delete, del]
subject: Computer Science 2
tags: [undergrad]
---
# 'Delete' Operator

> [!note]
> Used to free memory allocated with the 'new' operator. Is called on a pointer to dynamically allocated memory when it is no longer needed. Can delete a single variable/object or array.

> [!example]
> ```cpp
> delete PointerName;
> delete [] ArrayName;
> // Convention is to then set pointer to deleted memory to NULL
> PointerName = 0; || PointerName = nullptr;
> ArrayName = 0;

## References
1. [['New' Operator]]
2. [[Dynamic Memory Allocation]]
3. [[Memory Allocation]]