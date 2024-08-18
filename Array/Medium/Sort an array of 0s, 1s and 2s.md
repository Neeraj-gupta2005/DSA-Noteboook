
# Sort an array of 0s, 1s and 2s

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/sort-colors/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n * log n)` :
```cpp
void sortColors(vector<int>& nums) {
        sort(nums.begin(),nums.end());
    }
```
**Code** (Better Solution) `O(n)` :
```cpp
void sortColors(vector<int>& nums) {
        int count0 = 0, count1 = 0, count2 = 0;
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] == 0)
                count0++;
            if (nums[i] == 1)
                count1++;
            if (nums[i] == 2)
                count2++;
        }
        for (int i = 0; i < count0; i++) {
            nums[i] = 0;
        }
        for (int i = count0; i < count0 + count1; i++) {
            nums[i] = 1;
        }
        for (int i = count0 + count1; i < nums.size(); i++) {
            nums[i] = 2;
        }
    }
```
**Code**(Optimal Solution) `O(n)` :
```cpp
void sortColors(vector<int>& nums) {
        int n = nums.size();
        int low = 0;
        int mid = 0;
        int high = n-1;

        while(mid<=high){
            if(nums[mid]==0){
                swap(nums[low],nums[mid]);
                low++;
                mid++;
            }
            else if(nums[mid]==1){
                mid++;
            }
            else{
                swap(nums[mid],nums[high]);
                high--;
            }
        }
    }
```
