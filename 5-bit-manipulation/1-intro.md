### Binary Numbers
* Binary numbers are represented using `0` and `1` i.e `101`, `110` etc.
* We can convert binary to decimal. For example converting `101` to decimal,
    => `(101)2` (read as 101 base 2)
    => `1 * 2^2 + 0 * 2^1 + 1 * 2^0`
    => `4 + 0 + 1`
    => `5`
### Bitwise Operators

|  a  |  b  |`&`(bitwise and) |`\|`(bitwise or)|`^`(bitwise xor)| 
| --- | --- | ----------------| -------------  | -------------- | 
|  0  |  0  |        0        |       0        |        0       | 
|  0  |  1  |        0        |       1        |        1       | 
|  1  |  0  |        0        |       1        |        1       | 
|  1  |  1  |        1        |       1        |        0       | 

**Properties of ^(XOR) operator:-**
* XOR of a number with itself is 0(`5 ^ 5 = 0`).
* XOR of a number with zero gives the same number(`5 ^ 0 = 5`)

### Addition
* Addition rules
    * 0 + 0 = 0
    * 1 + 0 = 1
    * 1 + 1 = 10 (keep 0 and carry 1 to the left)
* Example:
```
   1 0 1
+    1 1
  ---------
 1 0 0 0   
```
### Subtraction
* For subtracting a from b, we have do some following steps
    * Find 2's complement of b by first inverting all the bits and then adding 1
    * Then add a to the 2's complement of b.

### Left Shift(<<) & Right Shift(>>) Operators 
* Left shift and right shift operator shifts bits to the left and right by the defined value respectively.
```
1001 << 2 = 100100 // shifts all bits to left by 2 places
1001 >> 2 = 10 // shifts all bits to right by 2 places
```
* `5 << 2 = 5 * 2^2 = 5 * 4 = 20`
* `5 >> 2 = 5 / 2^2 = 5 / 4 = 1` 