# Single Number

**Problem Statement**:
can be done using XOR
[Link to LeetCode](https://leetcode.com/problems/single-number/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution):
```cpp
int getSingleElement(vector<int> &arr) {
    int n = arr.size();

    for (int i = 0; i < n; i++) {
        int num = arr[i]; // selected element
        int cnt = 0;

        //find the occurrence using linear search:
        for (int j = 0; j < n; j++) {
            if (arr[j] == num)
                cnt++;
        }

        // if the occurrence is 1 return ans:
        if (cnt == 1) return num;
    }
    return -1;
}
```
**Code** (Better Solution using Map Data Structure):
```cpp
int getSingleElement(vector<int> &arr) {
    int n = arr.size();
    map<int, int> mpp;
    for (int i = 0; i < n; i++) {
        mpp[arr[i]]++;
    }

    //Find the single element and return the answer:
    for (auto it : mpp) {
        if (it.second == 1)
            return it.first;
    }
    return -1;
}

```
**Code**(Optimal Solution using XOR oeprator):
```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int xor1=0;
        for(int i = 0;i<nums.size();i++){
            xor1 ^= nums[i];
        }
        return xor1;
    }
};
```
