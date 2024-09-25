
# Bit Manipulation Tricks for Competitive Programming

## 1. Multiplying a number by a power of 2
- **Operation**: Left shift (`<<`)
- **Description**: Shifting a number `n` left by `k` positions is equivalent to multiplying `n` by `2^k`.
- **Example**:
    ```cpp
    int n = 5; // 5 * 2^3 = 40
    int result = n << 3; // result = 40
    ```

## 2. Dividing a number by a power of 2
- **Operation**: Right shift (`>>`)
- **Description**: Shifting a number `n` right by `k` positions is equivalent to dividing `n` by `2^k`.
- **Example**:
    ```cpp
    int n = 40; // 40 / 2^3 = 5
    int result = n >> 3; // result = 5
    ```

## 3. Checking if a number is odd or even
- **Operation**: Bitwise AND (`&`)
- **Description**: `n & 1` checks the least significant bit to determine if a number is odd (`1`) or even (`0`).
- **Example**:
    ```cpp
    if (n & 1) {
        // n is odd
    } else {
        // n is even
    }
    ```

## 4. Swapping two numbers without a temporary variable
- **Operation**: XOR (`^`)
- **Description**: You can swap two numbers using XOR.
- **Example**:
    ```cpp
    int a = 5, b = 3;
    a = a ^ b;
    b = a ^ b;
    a = a ^ b;
    // Now a = 3 and b = 5
    ```

## 5. Clearing the lowest set bit
- **Operation**: `n & (n - 1)`
- **Description**: Clears the lowest set bit of `n`.
- **Example**:
    ```cpp
    int n = 10; // Binary: 1010
    n = n & (n - 1); // n becomes 1000 (8)
    ```

## 6. Getting the lowest set bit
- **Operation**: `n & -n`
- **Description**: Isolates the lowest set bit of `n`.
- **Example**:
    ```cpp
    int n = 10; // Binary: 1010
    int lowestSetBit = n & -n; // lowestSetBit = 2 (binary 10)
    ```

## 7. Counting the number of set bits (Hamming Weight)
- **Operation**: Brian Kernighan's Algorithm
- **Description**: Continuously clears the least significant bit until the number becomes zero.
- **Example**:
    ```cpp
    int countSetBits(int n) {
        int count = 0;
        while (n) {
            n = n & (n - 1);
            count++;
        }
        return count;
    }
    ```

## 8. Checking if a number is a power of 2
- **Operation**: `n & (n - 1) == 0`
- **Description**: A number is a power of 2 if it has only one set bit.
- **Example**:
    ```cpp
    bool isPowerOfTwo(int n) {
        return n > 0 && (n & (n - 1)) == 0;
    }
    ```

## 9. Finding the XOR of all elements from 1 to n
- **Operation**: XOR (`^`)
- **Description**: Use the properties of XOR to calculate the cumulative XOR from 1 to n.
- **Example**:
    ```cpp
    int xor1ToN(int n) {
        if (n % 4 == 0) return n;
        if (n % 4 == 1) return 1;
        if (n % 4 == 2) return n + 1;
        return 0;
    }
    ```

## 10. Toggle the i-th bit
- **Operation**: XOR (`^`)
- **Description**: Toggle the i-th bit of `n` using `n ^ (1 << i)`.
- **Example**:
    ```cpp
    int n = 5; // Binary: 101
    int result = n ^ (1 << 1); // Toggles the 2nd bit (result = 7)
    ```

## 11. Set the i-th bit
- **Operation**: OR (`|`)
- **Description**: Set the i-th bit of `n` to `1` using `n | (1 << i)`.
- **Example**:
    ```cpp
    int n = 5; // Binary: 101
    int result = n | (1 << 1); // Sets the 2nd bit (result = 7)
    ```

## 12. Unset (clear) the i-th bit
- **Operation**: AND with NOT (`& ~`)
- **Description**: Unset the i-th bit of `n` using `n & ~(1 << i)`.
- **Example**:
    ```cpp
    int n = 7; // Binary: 111
    int result = n & ~(1 << 1); // Clears the 2nd bit (result = 5)
    ```

## 13. Checking if the i-th bit is set
- **Operation**: AND (`&`)
- **Description**: Check if the i-th bit is set using `n & (1 << i)`.
- **Example**:
    ```cpp
    bool isSet = (n & (1 << i)) != 0;
    ```

## 14. Rightmost different bit between two numbers
- **Operation**: XOR and AND
- **Description**: To find the rightmost bit where two numbers differ, use `x ^ y` and `& -1`.
- **Example**:
    ```cpp
    int rightmostDifferentBit(int x, int y) {
        return (x ^ y) & -(x ^ y);
    }
    ```
