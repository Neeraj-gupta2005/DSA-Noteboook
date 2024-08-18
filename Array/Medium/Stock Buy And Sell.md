
# Stock Buy And Sell

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(1)`  
  The space complexity is `O(1)` since no extra vector or array is used.

---

**Solution**:

**Code** (BruteForce Solution) `O(n^2)` :
```cpp
int maxProfit(vector<int>& prices) {
        int n = prices.size();
        int max_profit = 0;
        for(int i =0;i<n;i++){
            for(int j  = i+1 ;j<n;j++){
                if(prices[j]>prices[i]){
                    max_profit = max(max_profit,prices[j]-prices[i]);
                }  
            }
        }
        return max_profit;
    }
```
**Code**(Optimal Solution) `O(n)` :
```cpp
int maxProfit(vector<int>& arr) {
        int n = arr.size();
        int max_profit = 0;
        int min_price = INT_MAX;
        for(int i =0;i<n;i++){
            min_price = min(min_price,arr[i]);
            max_profit = max(max_profit , arr[i]-min_price);
        }
        return max_profit;
    }
```
