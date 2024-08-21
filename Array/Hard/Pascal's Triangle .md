
# Pascal's Triangle

## Variations of the Question :

- **Variation 1**: Given row number r and column number c. Print the element at position (r, c) in Pascal’s triangle.

- **Variation 2**: Given the row number n. Print the n-th row of Pascal’s triangle.

- **Variation 3**: Given the number of rows n. Print the first n rows of Pascal’s triangle.

---

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/pascals-triangle/)

### Complexities

- **Time Complexity**: `O(n^3)`  
  The time complexity is `O(n^3)` because of single loop.

- **Space Complexity**: `O(n^2)`  
  The space complexity is `O(n^2)` since no extra vector or array is used.

---

**Solution**:

**Code** `Variation 1` `O(n)` :
```cpp
int nCr(int n, int r) {
    long long res = 1;

    // calculating nCr:
    for (int i = 0; i < r; i++) {
        res = res * (n - i);
        res = res / (i + 1);
    }
    return res;
}

int pascalTriangle(int r, int c) {
    int element = nCr(r - 1, c - 1);
    return element;
}
```
**Code** (normal Solution) `Variation 2` `O(n^2)` :
```cpp
int nCr(int n, int r) {
    long long res = 1;

    // calculating nCr:
    for (int i = 0; i < r; i++) {
        res = res * (n - i);
        res = res / (i + 1);
    }
    return res;
}

void pascalTriangle(int n) {
    // printing the entire row n:
    for (int c = 1; c <= n; c++) {
        cout << nCr(n - 1, c - 1) << " ";
    }
    cout << "n";
}

```
**Code** (Optimal Solution) `Variation 2` `O(n)` :

<img src="https://static.takeuforward.org/wp/uploads/2023/04/Screenshot-2023-04-30-214245.png" alt="Screenshot" width="500"/>


```cpp
void pascalTriangle(int n) {
    long long ans = 1;
    cout << ans << " "; // printing 1st element

    //Printing the rest of the part:
    for (int i = 1; i < n; i++) {
        ans = ans * (n - i);
        ans = ans / i;
        cout << ans << " ";
    }
    cout << endl;
}
```
**Code**(Optimal Solution) `O(n^3)` :
```cpp
int nCr(int n, int r) {
    long long res = 1;

    // calculating nCr:
    for (int i = 0; i < r; i++) {
        res = res * (n - i);
        res = res / (i + 1);
    }
    return (int)(res);
}

vector<vector<int>> pascalTriangle(int n) {
    vector<vector<int>> ans;

    //Store the entire pascal's triangle:
    for (int row = 1; row <= n; row++) {
        vector<int> tempLst; // temporary list
        for (int col = 1; col <= row; col++) {
            tempLst.push_back(nCr(row - 1, col - 1));
        }
        ans.push_back(tempLst);
    }
    return ans;
}
```
