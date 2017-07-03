## get nth return value

```golang
func make_nth (n int) (func(a... interface{}) interface{}) {
         return func(args... interface{}) interface{}{
                 return args[n]
         }
}

var first = make_nth(0)
var second = make_nth(1)
var third = make_nth(2)
// etc.

var dir string = first(path.Split(os.Args[0])).(string)
```

## block gorutine

```golang
go func() {
	for {
		time.Sleep(time.Second)
	}
}()

select{} // block here for ever
```

## print 3 and padding with 0

```golang
fmt.Printf("%0*d", 5, 3)
```

## map as sets

```golang
sets := make(map[string]struct{})
sets["foo"] = struct{}{}
```