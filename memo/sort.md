## sort

```golang
	fields := []int{5, 3, 9, 7}
	sort.Ints(fields)
```

## reverse sort
```golang
	fields := []int{5, 3, 9, 7}
	sort.Sort(sort.Reverse(sort.IntSlice(fields)))
```