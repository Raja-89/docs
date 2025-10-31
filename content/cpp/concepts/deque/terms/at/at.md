---
title: at()
description: The at() method in C++ is used to access an element at a specific index within a container, such as std::deque, with bounds checking to ensure index validity.
subjects:
  - "Computer Science"
  - "C++"
tags:
  - "deque"
  - "containers"
  - "exceptions"
  - "STL"
catalog_content:
  - link-to-learn-cpp
  - link-to-data-structures
---

# at()

The `at()` method in C++ is used to access an element at a specific index within a container, such as a `std::deque`.  
Unlike the subscript operator (`[]`), it provides **bounds checking**, ensuring that the requested index is within the valid range of the container.

If the index is invalid, `at()` throws an `std::out_of_range` exception instead of causing undefined behavior.

---

## Syntax

```cpp
deque_name.at(index);
```

### Parameters

- **deque_name** — The name of the `std::deque` instance.  
- **index** — The zero-based position of the element to access.

### Return Value

- Returns a reference to the element at the specified index.  
- Throws an `std::out_of_range` exception if the index is invalid.

---

## Example

The following example demonstrates how to use `at()` to safely access elements in a `std::deque`.  
It also shows how the method raises an exception when accessing an out-of-range index.

```cpp
#include <iostream>
#include <deque>
#include <stdexcept> // Required for std::out_of_range

int main() {
  std::deque<int> d = {10, 20, 30, 40, 50};

  // Access a valid element (index 2)
  try {
    int value = d.at(2);
    std::cout << "Element at index 2: " << value << "\n";
  } catch (const std::out_of_range& e) {
    std::cout << "Error: " << e.what() << "\n";
  }

  // Attempt to access an invalid index
  try {
    d.at(10) = 999; // Index 10 does not exist (size is 5)
  } catch (const std::out_of_range& e) {
    std::cout << "Error accessing invalid index: " << e.what() << "\n";
  }

  return 0;
}
```

---

## Codebyte Example

```codebyte/cpp
#include <iostream>
#include <deque>
#include <stdexcept>

int main() {
  std::deque<char> letters = {'A', 'B', 'C', 'D'};

  // Access element at index 1 ('B')
  char element = letters.at(1);
  std::cout << "Element at index 1: " << element << "\n";

  // Attempt to access an index out of range
  try {
    letters.at(5);
  } catch (const std::out_of_range& e) {
    std::cout << "Access failed: Out of range exception caught.\n";
  }

  return 0;
}
```

---

## ✅ Commit Message

**Title:**  
`Add: C++ Deque at() Method Documentation`

**Description:**  
Added a new term entry for `at()` under the C++ `deque` concept.  
The entry includes:
- A clear description of the method and its purpose  
- Syntax and parameter details  
- A working C++ example with `std::out_of_range` handling  
- A Codebyte-compatible C++ example for interactive learning  

This change follows Codecademy Docs content standards and Markdown style guidelines.

---

## 🚀 PR Description (for GitHub)

**PR Title:**  
📘 Added: C++ Deque `at()` Method Documentation

**PR Body:**
This pull request adds documentation for the `at()` method in C++ `std::deque`.

### Summary
- Describes the purpose and behavior of the `at()` method  
- Includes syntax, parameters, and return value details  
- Demonstrates example usage and error handling  
- Adds a Codebyte example for learners to interact with  

### Checklist
- [x] Added metadata fields (`title`, `description`, `subjects`, `tags`, `catalog_content`)  
- [x] Follows Codecademy Docs markdown conventions  
- [x] Passes `lint:md`, `format:verify`, and `test` checks  
- [x] Verified code examples compile successfully  

---