
# Find the second largest number

**Problem Statement**:
[Link to GeeksForGeeks](https://www.geeksforgeeks.org/problems/second-largest3735/1)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of loops are not nested.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (Better Solution):
```cpp
class Solution {
  public:
    // Function returns the second
    // largest elements
    int print2largest(vector<int> &arr) {
        int largest = INT_MIN;
        int sec_largest = INT_MIN;
        for(int i =0;i<arr.size();i++){
            if(largest<arr[i]) largest = arr[i];
        }
        
        for(int i = 0;i<arr.size();i++){
            if(sec_largest < arr[i] && arr[i]!=largest)sec_largest = arr[i];
        }
        
        return sec_largest;
    }
};

```
**Code**(Optimal Solution):
```cpp
class Solution {
  public:
    // Function returns the second
    // largest elements
    int print2largest(vector<int> &arr) {
        int largest = INT_MIN;
        int sec_largest = INT_MIN;
        for(int i =0;i<arr.size();i++){
            if(largest<arr[i] ){
                sec_largest = largest;
                largest = arr[i];
            } 
            else if(sec_largest<arr[i] && arr[i]!=largest){
                sec_largest = arr[i];
            }
                
        }
        
        return sec_largest;
    }
};
