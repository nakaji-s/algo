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

## From json to map

```
// map[num:6.13 strs:[a b]]
byt := []byte(`{"num":6.13,"strs":["a","b"]}`)
var dat map[string]interface{}
if err := json.Unmarshal(byt, &dat); err != nil {
    panic(err)
}
fmt.Println(dat)
```

## From json to struct

```
// {1 [apple peach]}
type Response2 struct {
    Page   int      `json:"page"`
    Fruits []string `json:"fruits"`
}
str := `{"page": 1, "fruits": ["apple", "peach"]}`
res := Response2{}
json.Unmarshal([]byte(str), &res)
fmt.Println(res)
```

## Auto create struct definition from json
https://mholt.github.io/json-to-go/
