
# C++ Standard Template Library (STL) Functions

## Containers

### 1. `std::vector`
- **Description**: Dynamic array that resizes automatically when elements are inserted or deleted.
- **Functions**:
  - `push_back(val)`: Adds an element at the end.
  - `pop_back()`: Removes the last element.
  - `size()`: Returns the number of elements.
  - `clear()`: Removes all elements.
  - `begin() / end()`: Returns iterators to the start/end.
  - `at(index)`: Accesses the element at the given index with bounds checking.
  
### 2. `std::list`
- **Description**: Doubly linked list.
- **Functions**:
  - `push_back(val)`: Adds an element to the end.
  - `push_front(val)`: Adds an element to the front.
  - `pop_back()`: Removes the last element.
  - `pop_front()`: Removes the first element.
  - `size()`: Returns the number of elements.
  
### 3. `std::set`
- **Description**: Ordered container that stores **unique elements** in **ascending order**.
- **Functions**:
  - `insert(val)`: Inserts an element.
  - `erase(val)`: Removes an element.
  - `find(val)`: Returns an iterator to the element or `end()` if not found.
  - `size()`: Returns the number of elements.
  - `clear()`: Removes all elements.
- **Notes**: 
  - Elements are stored in **ascending order** by default.
  - It stores **unique elements**, meaning duplicates are ignored.

### 4. `std::map`
- **Description**: Stores key-value pairs in sorted order by key.
- **Functions**:
  - `insert({key, value})`: Inserts a key-value pair.
  - `erase(key)`: Removes an element by key.
  - `find(key)`: Returns an iterator to the key or `end()` if not found.
  - `at(key)`: Accesses the value by key with bounds checking.
  - `size()`: Returns the number of elements.

### 5. `std::unordered_map`
- **Description**: Hash table-based container for key-value pairs, unsorted.
- **Functions**:
  - `insert({key, value})`: Inserts a key-value pair.
  - `erase(key)`: Removes an element by key.
  - `find(key)`: Returns an iterator to the key or `end()` if not found.
  - `at(key)`: Accesses the value by key with bounds checking.
  - `size()`: Returns the number of elements.
  
---

## Algorithms

### 1. `std::sort`
- **Description**: Sorts elements in a range.
- **Syntax**: `sort(begin, end)`
- **Example**:
  ```cpp
  std::sort(arr.begin(), arr.end());
  ```

### 2. `std::reverse`
- **Description**: Reverses the order of elements in a range.
- **Syntax**: `reverse(begin, end)`
- **Example**:
  ```cpp
  std::reverse(arr.begin(), arr.end());
  ```

### 3. `std::accumulate`
- **Description**: Computes the sum of a range of elements.
- **Syntax**: `accumulate(begin, end, init_value)`
- **Example**:
  ```cpp
  int sum = std::accumulate(arr.begin(), arr.end(), 0);
  ```

### 4. `std::find`
- **Description**: Finds the first occurrence of an element.
- **Syntax**: `find(begin, end, val)`
- **Example**:
  ```cpp
  auto it = std::find(arr.begin(), arr.end(), 5);
  ```

---

## Utilities

### 1. `std::pair`
- **Description**: Combines two values into a single object.
- **Syntax**:
  ```cpp
  std::pair<int, int> p = {1, 2};
  ```
- **Functions**:
  - `first`: Access the first element.
  - `second`: Access the second element.
  
- **Using `std::pair` in `std::set`**: 
  - `std::pair` can be used in a `std::set`.
  - Pairs are stored and sorted based on the **first element** by default, and if the first elements are equal, the **second element** is used for sorting.

- **Example**:
  ```cpp
  #include <iostream>
  #include <set>

  int main() {
      std::set<std::pair<int, int>> mySet;

      mySet.insert({1, 4});
      mySet.insert({3, 2});
      mySet.insert({1, 2});
      mySet.insert({2, 3});
      mySet.insert({3, 2}); // Duplicate, will not be inserted

      for (const auto& p : mySet) {
          std::cout << "(" << p.first << ", " << p.second << ") ";
      }
      return 0;
  }
  ```

  **Output**:
  ```
  (1, 2) (1, 4) (2, 3) (3, 2)
  ```

---

## Iterators

### 1. `begin() / end()`
- **Description**: Returns iterators to the beginning and end of a container.

### 2. `advance()`
- **Description**: Advances the iterator by a specific number of positions.
- **Syntax**:
  ```cpp
  std::advance(it, n);
  ```

---

## Miscellaneous

### 1. `std::swap`
- **Description**: Swaps the values of two variables.
- **Syntax**:
  ```cpp
  std::swap(a, b);
  ```

### 2. `std::move`
- **Description**: Transfers ownership of resources from one object to another.
- **Syntax**:
  ```cpp
  std::move(src);
  ```

---

This is a brief overview of common STL containers, algorithms, and utilities in C++. You can expand this further based on your project needs.
