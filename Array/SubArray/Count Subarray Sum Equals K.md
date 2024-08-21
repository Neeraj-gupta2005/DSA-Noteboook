
# Subarray Sum Equals K

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/subarray-sum-equals-k/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n^3)` :
```cpp
int subarraySum(vector<int>& nums, int k) {
        int n = nums.size();
        int count=0;
        for(int i = 0;i<n;i++){
            for(int j = i;j<n;j++){
                int sum = 0;

                for(int k = i;k<=j;k++){
                    sum += nums[k];
                }

                if(sum == k){
                    count++;
                }
            }
        }
        return count;
    }
```
**Code** (Better Solution) `O(n^2)` :
```cpp
int subarraySum(vector<int>& nums, int k) {
        int n = nums.size();
        int count=0;
        for(int i = 0;i<n;i++){
            int sum = 0;
            for(int j = i;j<n;j++){
                sum += nums[j];
                if(sum == k){
                    count++;
                }
            }
        }
        return count;
    }
```
**Code**(Optimal Solution) `O(n)` :
```cpp
int subarraySum(vector<int>& nums, int k) {
        int n = nums.size();
        map<int,int> mpp;
        int count = 0;
        mpp[0] =1;
        int sum = 0;
        for(int i = 0;i<n;i++){
            sum += nums[i];

            int remove = sum - k;

            count += mpp[remove];

            mpp[sum]+=1;
        }
        return count;
    }
```
