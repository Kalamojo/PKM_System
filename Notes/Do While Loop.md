---
alias: []
subject: Computer Science 2
tags: [undergrad]
---
# Do While Loop

> [!note]
> Loop excecutes at least once and then repeats if conditions are met.

````ad-example
```cpp
#include <iostream>

int main() {
  int times;
  std::cout << "How many times shoud this run? ";
  std::cin >> times;

  do {
    std::cout << "Dogs" << std::endl;
    times--;
  } while (times > 0);
}

````

## References
1. [[C++ Iterator Statements]]
2. [[While Loop]]