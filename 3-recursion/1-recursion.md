### Recursion
* Recursion means the scenario when a function calls itself repeatedly(recursively). Functions get stacked up when called recursively. 
* Most often recursive call to a function accompanied by some base condition. Once base condition is satisfied the function returns and gets removed from the stack.
```cpp
// c++
void f(int n){
    if (n == 1) {
        return;
    }
    f(n-1) // function calls itself with different argument
}
int main(){
    f(3);
}
```
```
|         |
|   f(1)  |  f(1) returns first [f(1) satisfies base condition(n == 1) and returns without calling itself recursively]
|_________|
|   f(2)  |  f(2) returns second [f(2) calls f(1) waits for f(1) to be returned]
|_________|
|   f(3)  |  f(3) returns last [f(3) calls f(2) waits for f(2) to be returned]
-----------
```
* Lets say we want to find factorial of a given positive integer `n`. So first we have to think if we can convert the factorial function in such a way it would divide the whole problem to smaller problems and use solution of smaller problems to solve bigger problems.
```
f(n) calculates and returns factorial of n
n! = 1 x 2 x 3 x ... x n-1 x n
n! = f(n-1) x n
```
```cpp
// c++
int factorial(int n){
    if (n == 0) { // base condition(0! = 1)
        return 1;
    }
    return factorial(n-1) * n; // function calls itself with different argument
}
```
```go
// go
func factorial(n int) int {
	if n == 0 {
		return 1
	}
	return factorial(n-1) * n
}
```
* We want to find the sum of elements of a array up to given index using recursion.
```
f(index, arr) calculate returns the sum of elements of array up to n index
sum = arr[0] + arr[1] + arr[2] + ... + arr[n-1] + arr[n]
sum = f(n-1, arr) + arr[n]
```
```cpp
// c++
int sum(int idx, vector<int> arr ){
    if(idx < 0) {
        return 0;
    }
    return arr[idx] + sum(idx-1, arr);
}
```
```go
// go
func sum(n int, arr []int) int {
	if n < 0 {
		return 0
	}
	return sum(n-1, arr) + arr[n]
}
``` 
* Find sum of digits for a given number.
```
f(num) calculate and returns sum of all the digits present in num
sum = f(num / 10) + num % 10 (sum of remaining digits + sum of last digit)
```
```cpp
// c++
int sum(int num){
    if(num == 0){
        return 0;
    }
    return sum(num / 10) + num % 10;
}
```
```go
// go
func sum(n int) int {
	if n == 0 {
		return 0
	}
	return sum(n/10) + n%10
}
```
* Climbing stairs: You are climbing a staircase. It takes n steps to reach the top.
Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?
```
We can reach nth stair either from `n-1th` stair or from `n-2nd` stair as we have can climb 1 or 2 steps at once. So reaching nth stair is the sum of reaching `n-1th` stair plus `n-2nd` stair.
For base case `n == 0`, ways to going to 0th stair from either 1st stair(climbing 1 step) or 2nd stair(climbing 2 steps) is always 1.
```
```go
func climb(n int) int {
	// base cases
	if n == -1 { // ways to go to negative stair
		return 0
	}
	if n == 0 { // // ways to go to 0th stair
		return 1
	}

	return climb(n-1) + climb(n-2)
}
```
* Reverse a string with recursion.
```go
func reverse(i, j int, str *string) {
	if i > j {
		return
	}
	swap(i, j, str)

	reverse(i+1, j-1, str)
}

func swap(i, j int, str *string) {
	r := []rune(*str)
	r[i], r[j] = r[j], r[i]
	s := string(r)
	*str = s
}
```
* Find number of ways to travel from `(1, 1)` to `(NxM)` in `N x M` matrix. You can only travel to `N+1` or `M+1` cell.
```go
func matrixPath(n, m int) int {
	if n == 1 || m == 1 {
		return 1
	}
	return matrixPath(n-1, m) + matrixPath(n, m-1)
}
```