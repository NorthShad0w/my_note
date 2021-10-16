# go

Comliling for multiple operating system

change go env

GOOS="windows" GOARCH=amd64 go build -o test.exe test.go



strip debugging information and symbol table to reduce file size

```
go build -ldflags "-w -s"
```

datatype  _**:= can only be used inside functions**_

```
var num1 =5
var num2 int

firstName := "test"
test, test2, test3 := "asd", 123, 22
var test, test2 string, test3 int = "test", "test", 23

var (
    test string = "asd"
    test2 int = 123
)

ans, err := strconv.Atoi("123")
if err != nil{
    fmt.Println(err)
}

```



raw string 

```
string1 := `"asdas
asdasd
asdasd
asd"
====asdasda====
`

"asdas
asdasd
asdasd
asd"
====asdasda====
```

discover type

```
test := "asd"
fmt.Printf("%T\n",test)
fmt.Println(reflect.TypeOf(start))
fmt.Println(reflect.ValueOf(start).Kind())
```

input

```
fmt.Scanf("%d")
fmt.Scanf("%s")
```

function

```
func do() (int, bool){
    return 5,true
}
number,err := do(); !err{
    do_something()
} else {
    // handle the error
}


func do() int {
    return 1
}
func main(){
    var i func() int
    i = do
}
```

swich different from C, use fallthrough

array

```
var OS [3]string
OS[0] = "ios"
OS[1] = "Android"
OS[2] = "Windows"

nums := [...]int{1,1,1,1,1,1,1}


t := []int{1,2,3,4,5}
t = append(t, 6, 7, 8)

var table [5][6]string

for i, v := range OS{
    fmt.Println(i, v)
}

-----------------------
0 ios
1 Android
2 Windows

for _, v := range OS{
    fmt.Println(v)
}
-----------------------
ios
Android
Windows


for pos, char := range "test string"{
    fmt.Println(pos, char)
    fmt.Println("%d %c\n", pos, char)
}


```

pointers

```
func swap(a, b *int){
    *a, *b = *b, *a
}
swap(&a, &b)

```

struct

```
package main
import "fmt"
type point struct {
    x int
    y int
    z int
}
func (p point) length() int{
    
}
pt4 := point{1, 1, 1}
pt4.length()
```
