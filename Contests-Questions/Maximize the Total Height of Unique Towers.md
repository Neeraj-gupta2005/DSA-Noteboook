
# Maximize the Total Height of Unique Towers

You are given an array `maximumHeight`, 
where `maximumHeight[i]` denotes the maximum height the `ith` tower can be assigned.
Your task is to assign a height to each tower so that:

1. The height of the `ith` tower is a positive and does not exceed `maximumHeight[i]`.
2. No two towers have the same height

Return the `maximum` possible total sum of the tower heights. if its's not possible to assign heights, return `-1`.


**Example 1**:

Input: maximumHeight = `[2,3,4,3]`

Output: `10`

Explanation:

We can assign heights in the following way: `[1, 2, 4, 3]`.



**Solution**:

**Code** (optimal Solution):
```cpp
    long long maximumTotalSum(vector<int>& maximumHeight) {
        
        sort(maximumHeight.rbegin(),maximumHeight.rend());

        long long totalHeight = 0;
        int currentHeight = maximumHeight[0];

        for(int i = 0 ; i < maximumHeight.size() ; i++){
            if(currentHeight > maximumHeight[i]){
                currentHeight = maximumHeight[i];
            }
            if(currentHeight <= 0){
                return -1;
            }

            totalHeight += currentHeight ;
            currentHeight--;
        }
        return totalHeight;
    }
```
