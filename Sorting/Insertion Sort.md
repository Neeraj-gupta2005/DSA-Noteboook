# Insertion Sort

---

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is near about `O(n^2)` due to the two nested loops , but one is while loop that may not run completely.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---
## Solution

## Code (Easy)

```cpp
for(int i = 1 ;i<n;i++){
        int k = i;
        while(k>0 && arr[k-1]>arr[k]){
            swap(arr[k],arr[k-1]);
            k--;
        }
    }
```
## Code (medium)

```cpp
for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;

        // Move elements of arr[0..i-1] that are greater than key
        // to one position ahead of their current position
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
```
