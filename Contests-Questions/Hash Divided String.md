# Hash Divided String


You are given a string `s` of length `n` and an integer `k`, where `n` is a multiple of `k`. Your task is to hash the string `s` into a new string called `result`, which has a length of `n / k`.

## Steps

1. First, divide `s` into `n / k` substrings, each with a length of `k`.
2. Initialize `result` as an empty string.
3. For each substring (in order from the beginning):
   - The hash value of a character is the index of that character in the English alphabet (e.g., 'a' → 0, 'b' → 1, ..., 'z' → 25).
   - Calculate the sum of all the hash values of the characters in the substring.
   - Find the remainder of this sum when divided by 26, which is called `hashedChar`.
   - Identify the character in the English lowercase alphabet that corresponds to `hashedChar`.
   - Append that character to the end of `result`.
4. Return `result`.

## Example 1

- **Input:** `s = "abcd"`, `k = 2`
- **Output:** `"bf"`

**Explanation:**

- First substring: `"ab"`, hash value sum = 0 + 1 = 1, `1 % 26 = 1`, `result[0] = 'b'`.
- Second substring: `"cd"`, hash value sum = 2 + 3 = 5, `5 % 26 = 5`, `result[1] = 'f'`.

## Example 2

- **Input:** `s = "mxz"`, `k = 3`
- **Output:** `"i"`

**Explanation:**

- The only substring: `"mxz"`, hash value sum = 12 + 23 + 25 = 60, `60 % 26 = 8`, `result[0] = 'i'`.

## Constraints

- `1 <= k <= 100`
- `k <= s.length <= 1000`
- `s.length` is divisible by `k`.
- `s` consists only of lowercase English letters.


---

**Solution**:

**Code** (Better Solution):
```cpp
string stringHash(string s, int k) {
        int n = s.length();
        string result = "";

        for(int i = 0 ; i < n ; i += k){
            int sum = 0;
            for(int j = 0 ; j < k ; j++){
                sum += (s[i+j] - 'a');
            }
            int hashChar = sum % 26;

            result += (char)('a' + hashChar);
        }

        return result;
    }
```
