
# Leaders in an Array

**Problem Statement**:
[Link to GeeksForGeeks](https://www.geeksforgeeks.org/problems/leaders-in-an-array-1587115620/1)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O()` :
```cpp
vector<int> leaders(int n, int arr[]) {
        vector<int> result;
        for(int i = 0;i<n;i++){
            bool leader = true;
            
            for(int j =i+1 ;j<n;j++){
                if(arr[i]<arr[j]){
                    leader = false;
                    break;
                }
            }
            
            if(leader){
                result.push_back(arr[i]);
            }
        }
        return result;
    }
```
**Code**(Optimal Solution) `O()` :
```cpp
vector<int> leaders(int n, int arr[]) {
        vector<int> result;
        int leader = arr[n-1];
        result.push_back(leader);
        for(int i = n-2;i>=0;i--){
            
            if(arr[i]>=leader){
                result.push_back(arr[i]);
                leader = arr[i];
            }
        }
        reverse(result.begin(),result.end());
        return result;
    }
```
