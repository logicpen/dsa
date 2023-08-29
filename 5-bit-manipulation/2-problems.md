**Question 1:-** Find if a number is even or odd.

**Answer:-** The last digit of binary representation of odd number is always 1 and 0 incase of even number. So if we perform `and` operation between the given number and 1 we will get 1 incase of odd number and 0 incase of even number
```
1101 & 0001 = 0001
1100 & 0001 = 0000
```
```go
// golang
a := 4 // test for 4
if a&1 == 0 {
    fmt.Println("even")
} else {
    fmt.Println("odd")
}
```
**Question 2:-** Find if two integers have opposite signs or not.
**Answer :-** The left most bit is 0 incase of positive number and 1 incase of negative number. The xor operator would turn the left most bit to zero if both the numbers are of same sign(resulting number is positive) and to 1 if both the numbers are of opposite sign(resulting number is negative)
```go
a := 4
b := -4
if a^b > 0 {
    fmt.Println("different sign")
} else if a^b < 0 {
    fmt.Println("different")
}
```
**Question 3:-** Find the value of `ith` bit.
**Answer :-** We can left shift 1 `i` times and perform and(&)operation, if we get zero then we would know that ith bit is 0 and if we get non-zero number we would know it's 1.
```go
a := 0b101001 // count starts from left with index of the left most bit is zero
b := 1 << 3   // left shift 3 times
if (a & b) > 0 {
    fmt.Println("bit contains 1")
} else {
    fmt.Println("bit contains 0")
	}
```
**Question 4:-** Clear `ith` bit.
**Answer :-** 
```go
// clear 3rd bit i.e set it to zero
a := 0b101101
b := 1 << 3 // left shift 3 times(001000)
b = ^b      // do bitwise not on b (110111)
// short b := ^(1 << 3)
a = a & b   // a = 100101
fmt.Printf("%b\n", a)
```
**Question 5:-** Find the only 
