## get stdin by line

```golang
var sc = bufio.NewScanner(os.Stdin)

func nextLine() string {
    sc.Scan()
    return sc.Text()
}

func main() {
    line := nextLine()
}
```

## by word X times

```golang
func main() {
	var count int
	fmt.Scan(&count)
	field := make([]int, count)

	for i := 0; i < count; i++ {
		fmt.Scan(&field[i])
	}
```

## auto type conversion by word

```golang
func main() {
	var num [2]int
	fmt.Scan(&num[0], &num[1])
}
```

## scanf

```golang
func main() {
	var num [2]int
	fmt.Scanf("%d %d", &num[0], &num[1])
}
```

## 2D array pattern

```golang
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