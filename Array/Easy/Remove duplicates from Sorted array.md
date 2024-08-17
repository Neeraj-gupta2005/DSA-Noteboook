
# Remove duplicates from Sorted array

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code**(Optimal Solution):
```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i = 0;
        for(int j=1;j<nums.size();j++){
            if(nums[j]!=nums[i]){
                i++;
                nums[i]=nums[j];
            } 
        }
        return i+1;
    }
};
