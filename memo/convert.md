## num to string

```
fmt.Sprint(num)
```

## slice to set
```
func SliceToSet(src []string) map[string]struct{}{
	dst := map[string]struct{}{}
	for _, v := range src {
		dst[v] = struct{}{}
	}

	return dst
}
```