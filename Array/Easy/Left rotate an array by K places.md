# Left rotate an array by D places

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/rotate-array/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` for reversing the array.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code**(Better Solution):
```cpp
class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        int len=nums.size();
        if(len!=1){
        if(k>len) k = k % len;
        reverse(nums,0,len-1);
        reverse(nums,0,k-1);
        reverse(nums,k,len-1);
    }}
    void reverse(vector<int> &nums,int left,int right){
        while(left<right){
            swap(nums[left],nums[right]);
            left++;
            right--;
        }
    }
};
```
**Code**(Optimal Solution):
```cpp
class Solution {
public:
    void rotate(vector<int>& arr, int k) {
        int len = arr.size();
        if(len!=1){
            k=k%len;
            reverse(arr.begin(),arr.end()-k);
            reverse(arr.end()-k,arr.end());
            reverse(arr.begin(),arr.end());
        }
    }
};


