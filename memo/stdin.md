## get stdin by line

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

## auto type conversion by word

```
func main() {
	var num [2]int
	fmt.Scan(&num[0], &num[1])
}
```

## scanf

```
func main() {
	var num [2]int
	fmt.Scanf("%d %d", &num[0], &num[1])
}
```

## 2D array pattern

```
	x := 10
	y := 10
	field := make([][]int64, y)
	for j := 0; j < y; j++ {
		field[j] = make([]int64, x)
	}

	for j := 0; j < y; j++ {
		for i := 0 ; i < x; i ++ {
			fmt.Scan(&field[i][j])
		}
	}
```