## 12 to 24 hour time conversion

```golang
func main() {
	var s string
	fmt.Scan(&s)

	layout := "15:04:05PM"
	t, _ := time.Parse(layout, s)

	layout_out := "15:04:05"
	fmt.Println(t.Format(layout_out))
}
```