# Selection Sort
---


### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is `O(n^2)` due to the two nested loops , one for checking the minimum element after each iteration.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

## Solution

## Code

```cpp
void SelectionSort(vector<int>& arr, int n) {
    for(int i = 0;i<n;i++){
        int min_indx = i;
        for(int j = i+1 ;j<n;j++){
            if(arr[j]<arr[min_indx])min_indx = j;
        }
        swap(arr[i],arr[min_indx]);
    }
}

