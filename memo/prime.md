## get prime numbers simple

```
func getPrime(max int, current []int) []int {
	if len(current) == 0 {
		current = []int{2}
	}
	for i := current[len(current)-1] + 1; i < max; i++ {
		notPrime := false
		for _, n := range current {
			if i%n == 0 {
				notPrime = true
				break
			}
		}
		if notPrime == false {
			current = append(current, i)
		}
	}

	return current
}
```