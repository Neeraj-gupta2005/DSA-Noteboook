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
void merge(vector<int> &arr,int low,int mid,int high){
    vector <int> temp;
    int left = low;
    int right = mid+1;
    while(left <= mid && right <= high){
        if(arr[left]<=arr[right]){
            temp.push_back(arr[left]);
            left++;
        }
        else{
            temp.push_back(arr[right]);
            right++;
        }
    }

   while(left <= mid){
        temp.push_back(arr[left]);
        left++;
   }
   while(right <= high){
        temp.push_back(arr[right]);
        right++;
   }

   for(int i = low;i<=high;i++){
    arr[i]=temp[i-low];
   }
}
void mergeSort(vector <int> &arr,int low,int high){
    if(low < high){
        int mid = low + (high - low)/2;
        mergeSort(arr,low,mid);
        mergeSort(arr,mid+1,high);
        merge(arr,low,mid,high);
    }
}

