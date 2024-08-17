# Insertion Sort

---

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is near about `O(n^2)` due to the two nested loops , but one is while loop that may not run completely.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---
## Solution

## Code

```cpp
for(int i = 1 ;i<n;i++){
        int k = i;
        while(k>0 && arr[k-1]>arr[k]){
            swap(arr[k],arr[k-1]);
            k--;
        }
    }
