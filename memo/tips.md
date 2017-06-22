## get nth return value

```
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
