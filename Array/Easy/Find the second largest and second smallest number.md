
# Binary Search

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/binary-search/)

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is `O(n^2)` due to the two nested loops.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Explanation**:
Binary search works by repeatedly dividing the search interval in half. If the target value is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Continue until the value is found or the interval is empty.

**Code**:
```cpp
int binarySearch(vector<int>& nums, int target) {
    int left = 0;
    int right = nums.size() - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) {
            return mid;
        } else if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return -1;
}
