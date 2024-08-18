
# Longest Subarray with given Sum K(Positives and Negatives)

**Problem Statement**:
[Link to GeeksForGeeks](https://www.geeksforgeeks.org/problems/longest-sub-array-with-sum-k0809/1)

---

**Solution**:

**Code** (BruteForce Solution) `O(n^3)` :
```cpp
int lenOfLongSubarr(int arr[],  int n, int k) 
    { 
        int len = 0;
        for(int i =0;i<n;i++){
            
            for(int j = i ; j< n;j++){
                long long s = 0;
                for(int k = i;k<=j;k++){
                    s+=arr[k];
                }
                
                if(s == k){
                    len = max(len,j-i+1);
                }
            }
        }
        return len;
    } 
```
**Code**(Better Solution) `O(n^2)` :
```cpp
int lenOfLongSubarr(int arr[],  int n, int k) 
    { 
        int len = 0;
        for(int i =0;i<n;i++){
            long long s = 0;
            for(int j = i ; j< n;j++){
                s+=arr[j];
                if(s == k){
                    len = max(len,j-i+1);
                }
            }
        }
        return len;
    } 
```

**Code**(Optimal Solution) `O(n)`:
```cpp
int lenOfLongSubarr(int arr[],  int n, int k) 
    { 
        int sum = 0;
        int max_len  =0;
        map<long long,int> mpp;
        for(int i =0;i<n;i++){
            sum+=arr[i];
            if(sum == k){
                max_len = max(max_len,i+1);
            }
            int rem = sum - k;
            if(mpp.find(rem)!=mpp.end()){
                int len = i-mpp[rem];
                max_len = max(max_len,len);
            }
            if(mpp.find(sum)==mpp.end()){
                mpp[sum] = i;
            }
        }
        return max_len;
    } 
```
