
# Minimum Element After Replacement With Digit Sum

You are given an integer array `nums`.
You replace each element in `nums` with the sum of its digits.
Return the minimum element in `nums` after all replacements.


**Example 1**:

Input: nums = `[10,12,13,14]`

Output: `1`

Explanation:

`nums` becomes `[1, 3, 4, 5]` after all replacements, with minimum element 1.



**Solution**:

**Code** (optimal Solution):
```cpp
    int calcSum(int num){
        int sum = 0;
        while(num != 0){
            sum += num % 10;
            num /= 10;
        }
        return sum;
    }
    int minElement(vector<int>& nums) {
        vector <int> ans;
        for(auto i : nums){
            ans.push_back(calcSum(i));
        }
        return *min_element(ans.begin(),ans.end());
    }
```
