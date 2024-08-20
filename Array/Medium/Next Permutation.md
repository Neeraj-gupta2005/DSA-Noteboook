
# Next Permutation

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/next-permutation/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n)` :
```cpp
void nextPermutation(vector<int>& nums) {
        next_permutation(nums.begin(),nums.end());
    }
```
**Code**(Optimal Solution) `O()` :
```cpp
void nextPermutation(vector<int>& nums) {
        int n = nums.size();
        if (n <= 1)
            return;
        int index = -1;
        for (int i = n - 1; i > 0; i--) {
            if (nums[i] > nums[i - 1]) {
                index = i - 1;
                break;
            }
        }
        if (index == -1) {
            reverse(nums.begin(), nums.end());
            return;
        }
        for (int i = n - 1; i > index; i--) {
            if (nums[i] > nums[index]) {
                swap(nums[i], nums[index]);
                break;
            }
        }
        reverse(nums.begin() + index + 1, nums.end());
    }
```

