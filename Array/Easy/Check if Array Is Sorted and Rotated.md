
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

**Code** (Optimal Solution):

```

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

