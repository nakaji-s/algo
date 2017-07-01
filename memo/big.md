## handle big number

```golang
func fibonacci(t1, t2, n int64) *big.Int {
	if n == 1 {
		return big.NewInt(t1)
	}
	if n == 2 {
		return big.NewInt(t2)
	}
	ret := fibonacci(t1, t2, n-1)
	ret.Mul(ret, ret)
	ret.Add(ret, fibonacci(t1, t2, n-2))
	return ret
}
```