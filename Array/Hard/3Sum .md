
# 3 Sum 

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/3sum/)

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is `O(n^2)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n^3)` :
```cpp
for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            for (int k = j + 1; k < n; k++) {
                if (arr[i] + arr[j] + arr[k] == 0) {
                    vector<int> temp = {arr[i], arr[j], arr[k]};
                    sort(temp.begin(), temp.end());
                    st.insert(temp);
                }
            }
        }
    }
```
**Code** (Better Solution) `O(n^2 * logn(num of unique triplets))` :
```cpp
vector<vector<int>> threeSum(vector<int>& nums) {
        set<vector<int>> st;

        for (int i = 0; i < n; i++) {
            set<int> hashset;
            for (int j = i + 1; j < n; j++) {
                // Calculate the 3rd element:
                int third = -(arr[i] + arr[j]);

                // Find the element in the set:
                if (hashset.find(third) != hashset.end()) {
                    vector<int> temp = {arr[i], arr[j], third};
                    sort(temp.begin(), temp.end());
                    st.insert(temp);
                }
                hashset.insert(arr[j]);
            }
        }

        // store the set in the answer:
        vector<vector<int>> ans(st.begin(), st.end());
        return ans;
    }
```

**Code**(Optimal Solution) `O(n^2)` :
```cpp
vector<vector<int>> threeSum(vector<int>& nums) {
        sort(nums.begin(), nums.end());
        vector<vector<int>> ans;
        int n = nums.size();
        for (int i = 0 ;i < n; i++) {
            // dont take duplicate i value
            if (i != 0 && nums[i] == nums[i - 1])
                continue;
            int j = i+1;
            int k = n - 1;
            while (j < k) {
                int sum = nums[i] + nums[j] + nums[k];

                if (sum > 0)
                    k--;
                else if (sum < 0)
                    j++;

                else {
                    vector<int> temp = {nums[i], nums[j], nums[k]};
                    ans.push_back(temp);
                    j++;
                    k--;
                    while (j < k && nums[j] == nums[j - 1])
                        j++;
                    while (j < k && nums[k] == nums[k + 1])
                        k--;
                }
            }
        }
        return ans;
    }
```
