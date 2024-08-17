# Move Zeros to end

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/move-zeroes/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of loops are not nested.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code**(BruteForce Solution):
```cp
vector<int> moveZeros(int n, vector<int> a) {
    vector<int> temp;
    //copy non-zero elements
    for (int i = 0; i < n; i++) {
        if (a[i] != 0)
            temp.push_back(a[i]);
    }

    // number of non-zero elements.
    int nz = temp.size();
    for (int i = 0; i < nz; i++) {
        a[i] = temp[i];
    }

    //fill rest of the cells with 0:
    for (int i = nz; i < n; i++) {
        a[i] = 0;
    }
    return a;
}
```
**Code**(Optimal Solution):
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int i = 0;
        int len = nums.size();
        for (int j = 0; j < len; j++) {
            if (nums[j] != 0) {
                swap(nums[i], nums[j]);
                i++;
            }
            
        }
    }
};
```
