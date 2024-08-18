
# Two Sum

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/two-sum/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n^2)` :
```cpp
vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        for(int i = 0 ;i<n;i++){
            for(int j = i+1 ;j<n;j++){
                if(nums[i]+nums[j] == target){
                    return {i,j};
                }
            }
        }
        return{-1,-1};
    }
```
**Code**(Optimal Solution) `O(n)` :
```cpp
vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        map<int,int> mpp;
        for(int i = 0;i<n;i++){
            int find = target - nums[i]; 
            if(mpp.find(find)!=mpp.end()){
                return {i,mpp[find]};
            }
            mpp[nums[i]] = i;
        }
        return{-1,-1};
    }
```
