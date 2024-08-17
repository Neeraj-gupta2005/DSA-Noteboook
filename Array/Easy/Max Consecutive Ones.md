# Max Consecutive Ones

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/max-consecutive-ones/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of Single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code**(Optimal Solution):
```cpp
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int count1 = 0;
        int max_count = 0;
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] == 1)
                count1++;
            else {
                max_count = max_count < count1 ? count1 : max_count;
                count1 = 0;
            }
        }
        return max_count > count1 ? max_count : count1;
    }
};
```
