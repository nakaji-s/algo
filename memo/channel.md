## channel based ring buffer

https://content.pivotal.io/blog/a-channel-based-ring-buffer-in-go

``` golang
package main

import "fmt"

type RingBuffer struct {
    inputChannel  <-chan int
    outputChannel chan int
}

func NewRingBuffer(inputChannel <-chan int, outputChannel chan int) *RingBuffer {
    return &RingBuffer{inputChannel, outputChannel}
}

func (r *RingBuffer) Run() {
    for v := range r.inputChannel {
        select {
        case r.outputChannel <- v:
        default:
            <-r.outputChannel
            r.outputChannel <- v
        }
    }
    close(r.outputChannel)
}
func main() {
    in := make(chan int)
    out := make(chan int, 5)
    rb := NewRingBuffer(in, out)
    go rb.Run()

    for i := 0; i < 10; i++ {
        in <- i
    }

    close(in)

    for res := range out {
        fmt.Println(res)
    }
}
//Prints:
//4
//5
//6
//7
//8
//9
//
//Program exited.
```