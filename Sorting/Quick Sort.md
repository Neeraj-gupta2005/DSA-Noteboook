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
int part(vector<int> &arr ,int low,int high){
    int pivot  = arr[low];
    int i = low;
    int j = high;
    while(i<j){
        while(i<=high && arr[i]<=pivot){
            i++;
        }
        while(j>=low && arr[j]>pivot){
            j--;
        }
        if(i<j) swap(arr[i],arr[j]);
    }
    swap(arr[low],arr[j]);
    return j;
}
void quickSort(vector <int> &arr ,int low ,int high){
    if(low < high){
        int partition_index = part(arr,low,high);
        quickSort(arr,low,partition_index-1);
        quickSort(arr,partition_index+1,high);
    }
}
