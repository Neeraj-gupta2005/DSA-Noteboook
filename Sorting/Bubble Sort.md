
# Bubble Sort

**Description**:

Use two nested loop and compare the 2 adjacent elements if first one is greater than swap it.
---

**Solution**:

**Explanation**:
  hindi - do loop lagao I and J j loop ke andar j and j+1 value ko compare karo , if j > j+1 then swap kardo , j loop n-i-1 tak chalega

**Complexities**:
  *Time Complexity* - O(n^2) Because of the two nested loops.:
  *Space Complexity* - O(1) No extra vector or an array is used.:

**Code**:
```cpp
void binarySearch(vector<int>& arr, int n) {
    for(int i = 0 ; i<n-1;i++){
        for(int j=0 ;j<n-i-1;j++){
            if(arr[j]>arr[j+1]) swap(arr[j],arr[j+1]);
        }
    }
}
