
# Rearrange Array Elements by Sign

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/rearrange-array-elements-by-sign/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n)` :
```cpp
vector<int> rearrangeArray(vector<int>& nums) {
        vector <int> pos ;
        vector <int> neg ;
        int len = nums.size();
        for(int i = 0;i <len ;i++){
            //if positive
            if(nums[i]>0){
                pos.push_back(nums[i]);
            }
            else{
                neg.push_back(nums[i]);
            }
        }

        for(int i =0;i<len/2;i++){
            nums[2*i]= pos[i];
            nums[2*i+1]= neg[i];
        }
        return nums;
    }
```
**Code**(Optimal Solution) `O()` :
```cpp
vector<int> rearrangeArray(vector<int>& nums) {
        int pos_indx = 0;
        int neg_indx = 1;
        int len = nums.size();
        vector <int> result(len,0);
        for(int i = 0;i <len ;i++){
            //if positive
            if(nums[i]>0){
                result[pos_indx] = nums[i];
                pos_indx+=2;
            }
            else{
                result[neg_indx] = nums[i];
                neg_indx+=2;
            }
        }
        return result;
    }
```
