# Binary Search

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/binary-search/)

**Description**:
Implement a binary search algorithm that finds a target value in a sorted array.

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
