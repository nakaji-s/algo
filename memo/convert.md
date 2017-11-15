## num to string

```
fmt.Sprint(num)
```

## slice to set
```
sliceToSet := func (src []string) {
    dst := map[string]struct{}{}
    for _, v := range src {
        dst[v] = struct{}{}
    }
}

ret := sliceToSet([]string{"apple", "orange", "banana"})
```