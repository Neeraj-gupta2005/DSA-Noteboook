
# Majority Element II

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/majority-element-ii/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used .

---

**Solution**:

**Code** (BruteForce Solution) `O(n^2)` :
```cpp
vector<int> majorityElement(vector<int>& nums) {
        vector<int> ans;
        int n = nums.size();
        for (int i = 0; i < n; i++) {
            int el = nums[i];
            int count = 0;

            if (ans.size() == 0 || ans[0] != el) {
                for (int j = 0; j < n; j++) {
                    if (nums[j] == el) {
                        count++;
                    }
                }
                if (count > (n / 3)) {
                    ans.push_back(el);
                }
            }

            if (ans.size() == 2) {
                break;
            }
        }
        return ans;
    }
```
**Code** (Better Solution) `O(n)` :
```cpp
vector<int> majorityElement(vector<int>& nums) {
        vector<int> ans;
        int n = nums.size();
        map <int,int> mpp;
        for (int i = 0; i < n; i++) {
            mpp[nums[i]]++;
        }
        for(auto it:mpp){
            if(it.second > n/3){
                ans.push_back(it.first);
            }
        }
        return ans;
    }
```
**Code** (Better Solution 2) `O(n)` :
```cpp
vector<int> majorityElement(vector<int>& nums) {
        vector<int> ans;
        int n = nums.size();
        map <int,int> mpp;
        int mini = (n/3)+1;
        for (int i = 0; i < n; i++) {
            mpp[nums[i]]++;
            if(mpp[nums[i]] == mini){
                ans.push_back(nums[i]);
            }
            if(ans.size()==2)break;
        }
        return ans;
    }
```
**Code**(Optimal Solution) `O(n)` :
```cpp
vector<int> majorityElement(vector<int>& nums) {
        int n = nums.size();
        int count1 = 0 , count2 = 0;
        int el1 = INT_MIN , el2 = INT_MIN;
        for (int i = 0; i < n; i++) {
            if(count1 == 0 && nums[i] != el2){
                count1 = 1;
                el1 =nums[i];
            }
            else if(count2 == 0 && nums[i] != el1){
                count2 = 1;
                el2 =nums[i];
            }

            else if(nums[i]==el1) count1++;
            else if(nums[i]==el2) count2++;
            else{
                count1--;
                count2--;
            }
        }
        vector<int> ls;
        count1 = 0, count2 = 0;
        for (int i = 0; i < n; i++) {
            if (nums[i] == el1) count1++;
            if (nums[i] == el2) count2++;
        }

        int mini = int(n / 3) + 1;
        if (count1 >= mini) ls.push_back(el1);
        if (count2 >= mini) ls.push_back(el2);
        return ls;
    }
```
