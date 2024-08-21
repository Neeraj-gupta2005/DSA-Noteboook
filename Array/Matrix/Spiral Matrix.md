
# Spiral Matrix

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/spiral-matrix/description/)

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is `O(n)` because of nested loops loop.

- **Space Complexity**: `O(n)`  
  The space complexity is `O(n)` since an extra vector is used to store the output.

---

**Solution**:

**Code**(Optimal Solution) `O(n^2)` :
```cpp
vector<int> spiralOrder(vector<vector<int>>& matrix) {
        int m = matrix.size();
        int n = matrix[0].size();
        vector<int> ans;
        int top = 0;
        int left = 0;
        int right = n -1;
        int bottom = m-1;

        while(left<=right && top <= bottom){

            // for moving top left to right
            for(int i = left ;i<=right;i++){
                ans.push_back(matrix[top][i]);
            }
            top++;

            //for moving top right to bottom
            for(int i = top ; i<=bottom ; i++){
                ans.push_back(matrix[i][right]);
            }
            right--;

            //for moving bottom right to left
            if(top<=bottom){
                for(int i = right ; i>=left ; i--){
                    ans.push_back(matrix[bottom][i]);
                }
                bottom--;
            }

            //for moving bottom left to top
            if(left<=right){
                for(int i = bottom ; i>=top ; i--){
                    ans.push_back(matrix[i][left]);
                }
                left++;
            }

        }
        return ans;
    }
```
