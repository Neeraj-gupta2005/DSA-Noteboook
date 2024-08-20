
# Set Matrix Zeroes

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/set-matrix-zeroes/)

### Complexities

- **Time Complexity**: `O(n^2)`  
  The time complexity is `O(n)` because of double loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n^3)` :
```cpp
void setMinusRow(vector<vector<int>>&matrix ,int i ,int n){
        for(int j = 0;j<n;j++){
            if(matrix[i][j]!=0)
                matrix[i][j] = -1;
        }
    }
    void setMinusCol(vector<vector<int>>&matrix ,int j ,int m){
        for(int i = 0;i<m;i++){
            if(matrix[i][j]!=0)
                matrix[i][j] = -1;
        }
    }
    void setZeroes(vector<vector<int>>& matrix) {
        int m = matrix.size();
        int n = matrix[0].size();

        for(int i = 0;i<m;i++){
            for(int j = 0;j<n;j++){
                if(matrix[i][j] == 0){
                    setMinusRow(matrix , i , n);
                    setMinusCol(matrix , j , m);
                }
            }
        }

        for(int i = 0;i<m;i++){
            for(int j = 0;j<n;j++){
                if(matrix[i][j] == -1){
                    matrix[i][j] = 0;
                }
            }
        }
    }
```
**Code** (Better Solution) `Time Compexity O(n^2)` `Space Compexity O(n^2)` :
```cpp
void setZeroes(vector<vector<int>>& matrix) {
        int m = matrix.size();
        int n = matrix[0].size();
        vector <int> rows(m,0);
        vector <int> cols(n,0);
        for(int i = 0;i<m;i++){
            for(int j = 0;j<n;j++){
                if(matrix[i][j] == 0){
                    rows[i] = 1;
                    cols[j] = 1;
                }
            }
        }

        for(int i = 0;i<m;i++){
            for(int j = 0;j<n;j++){
                if(rows[i] || cols[j]){
                    matrix[i][j] = 0;
                }
            }
        }
    }
```
**Code**(Optimal Solution) `Time Compexity O(n^2)` `Space Compexity O(1)` :
```cpp
void setZeroes(vector<vector<int>>& matrix) {
        int m = matrix.size();
        int n = matrix[0].size();
        int col0 = 1;
        
        //mark first row and col value to zero if zero is found
        for(int i = 0 ; i<m;i++){
            for(int j = 0 ; j<n;j++){
                if(matrix[i][j]==0){
                    matrix[i][0] = 0;

                    if(j == 0){
                        col0 = 0;
                    }
                    else{
                        matrix[0][j] = 0;
                    }
                }
            }
        }

        // set the element to zero except row 0 and col 0
        for(int i = 1 ; i<m;i++){
            for(int j = 1 ; j<n;j++){
                if(matrix[i][0] == 0 || matrix[0][j] == 0){
                    matrix[i][j] = 0;
                }
            }
        }

        if(matrix[0][0] == 0){
            for(int j = 1; j< n ;j++){
                matrix[0][j] = 0;
            }
        }
        if(col0 == 0){
            for(int i = 0; i< m ;i++){
                matrix[i][0] = 0;
            }
        }

    }
```
