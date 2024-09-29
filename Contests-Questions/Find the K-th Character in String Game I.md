
# Find the K-th Character in String Game I

Alice and Bob are playing a game. Initially, Alice has a string `word = a`
You are given a positive integer `k`.
Now Bob will ask Alice to perform the following operation forever:
- Generate a new string by **changing** each `character` in word to its **next** character in the English alphabet, and **append** it to the original `word`.

for example, performing the operation on `"c"` generates `"cd"` and performing the operation on `"zb"` generates `"xbac"`

Return the value of the `Kth` character in `word`, after enough operations have been done for `word` to have at least `k` characters.

**Note** that the character `z` can be changed to `a` in the operations;

**Example 1**:

Input: k = 5

Output: `b`

Explanation:

Initially, `word = "a"`. We need to do the operation three times:
- Generated string is `"b"`, `word` becomes `"ab"`.
- Generated string is `"bc"`, `word` becomes `"abbc"`.
- Generated string is `"bccd"`, `word` becomes `"abbcbccd"`.



**Solution**:

**Code** (optimal Solution):
```cpp
    char kthCharacter(int k) {
        string givenWord = "a";

        while(givenWord.size() < k){
            string newWord = "";

            for(char c : givenWord){
                newWord += c == 'z' ? 'a' : c +1;
            }
            givenWord += newWord;
        }
        return givenWord[k-1];
    }
```
