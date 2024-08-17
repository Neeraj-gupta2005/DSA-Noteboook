# Quick Sort
  Quick Sort is a divide-and-conquer algorithm like the Merge Sort. But unlike Merge sort, this algorithm does not use any extra array for sorting(though it uses an auxiliary stack space). So, from that perspective, Quick sort is slightly better than Merge sort.
---

### Complexities

- **Time Complexity**: `O(n log n)`  
  The time complexity is `O(n log n)` due to the two nested loops , but in a Worst case it can be O(n^2).

- **Space Complexity**: `O(n)`  
  The space complexity is `O(n)` the space complexity depends on the recursion stack depth. In the best and average cases, the recursion depth is 
  𝑂(log 𝑛), but in the worst case, it can be O(n).

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
