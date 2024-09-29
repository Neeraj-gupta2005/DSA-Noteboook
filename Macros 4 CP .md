
# Competitive Programming Template

## Loop Templates
Loops are used extensively, and competitive programmers often define macros for shorter loops.

### For Loop Macros:
```cpp
#define rep(i, a, b) for (int i = a; i < b; i++)   // Loop from a to b-1
#define rrep(i, a, b) for (int i = a; i >= b; i--) // Reverse loop from a to b
#define all(x) (x).begin(), (x).end()              // To iterate over the entire container
```

### Example Usage:
```cpp
rep(i, 0, n) {
    // Code
}

rrep(i, n-1, 0) {
    // Reverse loop code
}
```
## Printing

### Vectors:
```cpp
#define print_vector(v) { for(auto x : v) cout << x << " "; cout << endl; } // Initializes a macro for Printing vector
```
### Arrays:
```cpp
#define print_array(arr, size) { for(int i = 0; i < size; i++) cout << arr[i] << " "; cout << endl; } // Initializes a macro for Printing array
```

## Type Aliases:
Type aliases are used to shorten commonly used types and make the code more readable.

```cpp
using ll = long long;            // For large integers
using pii = pair<int, int>;       // For pairs of integers
using vi = vector<int>;           // For a vector of integers
using vvi = vector<vector<int>>;  // For a 2D array (vector of vector of integers)


for pair we can also use
auto pi = make_pair(1,2); // make_pair returns pair<int,int> which auto sets to pi
```
### Example Usage:
```cpp
// Using ll for large integers
    ll largeNumber = 1e18; // Example of a large integer
    cout << "Large Number: " << largeNumber << endl;

    // Using pii for pairs of integers
    pii coordinates = make_pair(3, 4);
    cout << "Coordinates: (" << coordinates.first << ", " << coordinates.second << ")" << endl;

    // Using vi for a vector of integers
    vi numbers = {1, 2, 3, 4, 5};
    cout << "Vector elements: ";
    for (int num : numbers) {
        cout << num << " ";
    }
    cout << endl;

    // Using vvi for a 2D vector (array of arrays)
    vvi matrix = {{1, 2, 3}, {4, 5, 6}, {7, 8, 9}};
    cout << "2D Array (Matrix):" << endl;
    for (const auto& row : matrix) {
        for (int value : row) {
            cout << value << " ";
        }
        cout << endl;
    }
```


## size initialize
```cpp
#define sz(a) (int)(a).size() // Initializes size
```

## Common Shortcuts for Data Structures:

### Pair:
Useful for storing two values.
```cpp
#define pii pair<int, int>
```

### Priority Queue:
```cpp
#define MAX_HEAP(type) priority_queue<type>
#define MIN_HEAP(type) priority_queue<type, vector<type>, greater<type>>

Use Case:
MAX_HEAP(int) maxHeap;
```

### Common Modulo Operation:
```cpp
#define MOD 1000000007
#define mod(a) ((a) % MOD)
```

## Common Functions:
Utility functions for common tasks like finding the minimum or maximum of three or more elements.

```cpp
#define min3(a, b, c) min(a, min(b, c))
#define max3(a, b, c) max(a, max(b, c))
```

## Debugging Macros:
Quick macros to print variable values for debugging purposes.

```cpp
#define debug(x) cout << #x << " = " << x << endl;
```


## General Template:
Here’s a full example template that competitive programmers might use:

```cpp
#include <bits/stdc++.h>
using namespace std;

// Typedefs for shorter types
using ll = long long;  
using pii = pair<int, int>;       
using vi = vector<int>;           
using vvi = vector<vector<int>>;  


// Loop macros
#define rep(i, a, b) for (int i = a; i < b; i++)
#define rrep(i, a, b) for (int i = a; i >= b; i--)
#define all(x) (x).begin(), (x).end()

// Constants
const int MOD = 1000000007;
const int INF = 1e9;

// Utility functions
#define min3(a, b, c) min(a, min(b, c))
#define max3(a, b, c) max(a, max(b, c))

// Debugging
#define debug(x) cout << #x << " = " << x << endl;

```

## Use of `all(x)`
The `#define all(x) (x).begin(), (x).end()` macro is a common shortcut used to work with the full range of a container.

### Purpose:
- **all(x)** expands to `(x).begin(), (x).end()`.
- It is useful in functions like sorting, reversing, finding minimum/maximum, and more.

### Common Use Cases:

#### Sorting a Vector:
```cpp
sort(all(vec));
```

#### Reversing a Vector:
```cpp
reverse(all(vec));
```

#### Finding Minimum/Maximum in a Vector:
```cpp
auto min_elem = *min_element(all(vec));
auto max_elem = *max_element(all(vec));
```


### Key Points:
- **Saves Time**: Instead of repeatedly writing `begin()` and `end()`, you can shorten your code.
- **Improves Readability**: Especially in contests where time matters, `all(x)` makes your intentions clear and reduces clutter.
- **Reduces Errors**: Less code means fewer chances of making mistakes.
