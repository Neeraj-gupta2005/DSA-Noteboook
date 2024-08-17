# Bubble Sort

---

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is `O(n^2)` due to the two nested loops.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

## Solution

## Code without Recursion

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
```
## Code using Recursion

```cpp
void bubbleSort(vector<int> &arr,int n){
    if(n==1) return;
    for(int j = 0;j<n-1;j++){
        if(arr[j]>arr[j+1])swap(arr[j],arr[j+1]);
    }

    bubbleSort(arr,n-1);
}

