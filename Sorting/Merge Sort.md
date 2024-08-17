# Merge Sort

---

### Complexities

- **Time Complexity**: `O(n log n)`  
  The time complexity is `O(n log n)` due to the two nested loops.

- **Space Complexity**: `O(n)`  
  The space complexity is `O(n)` an extra array to store the result when merging.

---

## Solution

## Code

```cpp
void bubbleSort(vector<int>& arr, int n) {
    for(int i = 0; i < n - 1; i++) {
        for(int j = 0; j < n - i - 1; j++) {
            if(arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}

