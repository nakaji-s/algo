## bit counter

```golang
func countBits(bits int64) int64 {
	bits = (bits & 0x55555555) + (bits >> 1 & 0x55555555)
	bits = (bits & 0x33333333) + (bits >> 2 & 0x33333333)
	bits = (bits & 0x0f0f0f0f) + (bits >> 4 & 0x0f0f0f0f)
	bits = (bits & 0x00ff00ff) + (bits >> 8 & 0x00ff00ff)
	return (bits & 0x0000ffff) + (bits >> 16 & 0x0000ffff)
}
```

## to upper case

``` golang
'a' & '_'
```

## to lower case

```golang
'A' | ' '
```

##  is 2 to the power of n

```golang
n & (n - 1) == 0
```

##  is (2 to the power of n) - 1

```golang
n & (n + 1) == 0
```

## abs except INT_MIN

```golang
func abs(n int) int {
	sign := n >> 31
	return (n ^ sign) - sign
}
```