
# Majority Element

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/majority-element/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n^2)` :
```cpp
int majorityElement(vector<int>& nums) {
        int n = nums.size();
        for(int i =0;i<n;i++){
            int count=0;
            for(int j = 0;j<n;j++){
                if(nums[i] == nums[j]) count++;
            }

            if(count > n/2){
                return nums[i];
            }
        }
        return -1;
    }
```
**Code** (Better Solution) `O(n)` :
```cpp
int majorityElement(vector<int>& nums) {
        int n = nums.size();
        map<int,int> mpp;
        for(int i =0;i<n;i++){
            mpp[nums[i]]++;
        }
        for(auto it : mpp){
            if(it.second > n/2){
                return it.first;
            }
        }
        return -1;
    }
```
**Code**(Optimal Solution) `O(n)` :
```cpp
int majorityElement(vector<int>& nums) {
      int n = nums.size();
      int candi = nums[0];
      int count =1;
      for(int i=1;i<n;i++){
          if(nums[i]==candi){
              count++;
          }
          else{
              count--;
              if(count == 0){
                  candi = nums[i];
                  count = 1;
              }
          }
      }
      return candi;
}
```
