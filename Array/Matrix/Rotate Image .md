
# Rotate Image

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/rotate-image/description/)

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is `O(n^2)` because of double loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `Time Compexity O(n^2)` `Space Compexity O(n^2)` :
```cpp
void rotate(vector<vector<int>>& matrix) {
        int n = matrix.size();
        vector<vector<int>> result(n, vector<int>(n, 0));
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                result[j][n - i - 1] = matrix[i][j];
            }
        }
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matrix[i][j] = result[i][j];
            }
        }
}
```
**Code**(Optimal Solution) `Time Compexity O(n^2)` `Space Compexity O(1)` :
```cpp
void rotate(vector<vector<int>>& matrix) {
        int n = matrix.size();
        
        for(int i =0;i<n;i++){
            for(int j=i+1;j<n;j++){
                swap(matrix[i][j],matrix[j][i]);
            }
        }
        for(int i =0;i<n;i++){
           reverse(matrix[i].begin(),matrix[i].end());
        }
    }
```
