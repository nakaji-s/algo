package memo

## To json string

```
// true
bolB, _ := json.Marshal(true)
fmt.Println(string(bolB))

// 1
intB, _ := json.Marshal(1)
fmt.Println(string(intB))

// 2.34
fltB, _ := json.Marshal(2.34)
fmt.Println(string(fltB))

// "gopher"
strB, _ := json.Marshal("gopher")
fmt.Println(string(strB))

// ["apple","peach","pear"]
slcD := []string{"apple", "peach", "pear"}
slcB, _ := json.Marshal(slcD)
fmt.Println(string(slcB))

// {"apple":5,"lettuce":7}
mapD := map[string]int{"apple": 5, "lettuce": 7}
mapB, _ := json.Marshal(mapD)
fmt.Println(string(mapB))

// {"Page":1,"Fruits":["apple","peach","pear"]}
type Response1 struct {
    Page   int
    Fruits []string
}
res1D := &Response1{
    Page:   1,
    Fruits: []string{"apple", "peach", "pear"}}
res1B, _ := json.Marshal(res1D)
fmt.Println(string(res1B))

// {"page":1,"fruits":["apple","peach","pear"]}
type Response2 struct {
    Page   int      `json:"page"`
    Fruits []string `json:"fruits"`
}
res2D := &Response2{
    Page:   1,
    Fruits: []string{"apple", "peach", "pear"}}
res2B, _ := json.Marshal(res2D)
fmt.Println(string(res2B))
```