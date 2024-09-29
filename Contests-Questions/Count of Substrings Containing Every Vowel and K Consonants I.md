
# Count of Substrings Containing Every Vowel and K Consonants I

You are given a string `word` and a **non-negative** integer `k`.
Return the toal number of substrings of `word` that contains every vowel (`'a'`,`'e'`,`'i'`,`'o'`,and`'u'`) **at least** once **exactly** `k` consonants.


**Example 1**:

Input: word  = `"aeioqq"`, k = 1

Output: `0`

Explanation:

there is no substring with every vowel


**Example 2**:

Input: word  = `"ieaouqqieaouqq"`, k = 1

Output: `3`

Explanation:

The substrings with every vowel and one consonant are:
- `word[0..5]`, which is `"ieaouq"`.
- `word[6..11]`, which is `"qieaou"`.
- `word[7..12]`, which is `"ieaouq"`.

**Solution**:

**Code** (optimal Solution):
```cpp
    bool isVowel(char c){
        return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u';
    }
    int countOfSubstrings(string word, int k) {
        int n = word.size();
        int result = 0;

        for(int i = 0; i < n ; i++ ){
            unordered_set <char> st ;
            int consonants = 0;
            for(int j = i ; j < n ; j++){
                char c = word[j];
                if(isVowel(c)){
                    st.insert(c);
                }else{
                    consonants++;
                }
                
                if(st.size() == 5 && consonants == k){
                    result++;
                }
                if(consonants > k){
                    break;
                }
            }
        }
        return result;
    }
```
