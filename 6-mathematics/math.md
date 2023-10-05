### Sieve Of Eratosthenes
* In this method we would create an array of boolean of length equals to the number up to which we need to calculate the prime numbers. If we need to check if let's say if 7 is prime or not, we would go the the 7th index of array and check the boolean stored (if true then 7 is prime)
```go
func sieveOfEratosthenes(num int) {
	arr := make([]bool, num+1)
	for i := 0; i <= num; i++ {
		arr[i] = true
	}
	arr[0] = false // default values
	arr[1] = false // default values

	for i := 2; i*i < num; i++ {
		if arr[i] {
			for j := i * 2; j <= num; j += i {
				arr[j] = false
			}
		}

	}
	fmt.Println(arr)
}

```
### Calculate power