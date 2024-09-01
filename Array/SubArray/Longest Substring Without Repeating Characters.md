
# Longest Substring Without Repeating Characters

**Problem Statement**:
[Link to LeetCode](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)

### Complexities

- **Time Complexity**: `O(n)`  
  The time complexity is `O(n)` because of single loop.

- **Space Complexity**: `O(min(m,n))`  
  The space complexity is `O(min(m,n))` where m is the size of the character set (e.g., 26 for lowercase English letters).

---

**Solution**:
**Code**(Optimal Solution) `O(n)` :
```cpp
int lengthOfLongestSubstring(string s) {
        unordered_set <char> mpp;
        int start = 0;
        int maxLength = 0;
        for(int end = 0 ; end < s.size() ; end++){

            while(mpp.find(s[end]) != mpp.end()){
                mpp.erase(s[start]);
                start++;
            }
            mpp.insert(s[end]);
            maxLength = maxLength < (end - start +1) ? (end - start +1) : maxLength;
        }
        return maxLength;
    }
```
