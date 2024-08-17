
# Check if Array Is Sorted and Rotated

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of only 1 loop.

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
    bool check(vector<int>& nums) {
        int len=nums.size();
        int count=0;
        for(int i = 0 ; i<len;i++){
            if(nums[i] > nums[(i+1) % len] ) count++;
            if(count>1) return false;
        }
        return true;
    }
};
