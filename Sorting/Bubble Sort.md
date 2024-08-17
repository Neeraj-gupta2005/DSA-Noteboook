
# Bubble Sort

**Description**:

Use two nested loop and compare the 2 adjacent elements if first one is greater than swap it.
---

**Solution**:

**Explanation**:
Binary search works by repeatedly dividing the search interval in half. If the target value is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Continue until the value is found or the interval is empty.

**Complexities**
  *Time Complexity* - O(n^2) Because of the two nested loops. 
  *Space Complexity* - O(1) No extra vector or an array is used.

**Code**:
```cpp
void binarySearch(vector<int>& arr, int n) {
    for(int i = 0 ; i<n-1;i++){
        for(int j=0 ;j<n-i-1;j++){
            if(arr[j]>arr[j+1]) swap(arr[j],arr[j+1]);
        }
    }
}
