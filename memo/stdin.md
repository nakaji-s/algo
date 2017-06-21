* get stdin by line

```
var sc = bufio.NewScanner(os.Stdin)

func nextLine() string {
    sc.Scan()
    return sc.Text()
}

func main() {
    line := nextLine()
}
```