## Replace string with any rule

```golang
	str := "ab(cdurf)e"

	re, _ := regexp.Compile(`(\(.*\))`)
	cb := func(s string) string {
		return strings.ToUpper(s)
	}

	str = re.ReplaceAllStringFunc(str, cb)
```
