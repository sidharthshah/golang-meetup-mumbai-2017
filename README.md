# Summary of [Golang Talk](https://www.meetup.com/Mumbai-GoLang-Meetup/events/237780164/?comment_table_id=250951560&comment_table_name=reply)

- We will be building P2P chat application called Whisper
- [Slides](https://talks.golang.org/2017/state-of-go.slide#2)
- [A Tour of Go](https://tour.golang.org/welcome/1) is a good reference 
- This code lab is divived into 8 exercises
- [Visual Studio Code](https://code.visualstudio.com/) is an open source editor like Atom. [Setting Go Development Enviroment with Visual Studio Code](https://rominirani.com/setup-go-development-environment-with-visual-studio-code-7ea5d643a51a#.xnf3r3ns0)
- [goimports](https://godoc.org/golang.org/x/tools/cmd/goimports) is a tool which does static analysis on existing code and figure out what to import
- [GoSublime](https://github.com/DisposaBoy/GoSublime) is a recommended plugin for Sublime

## Setting up Go

1. Create workspace
	- `mkdir $HOME/go`
	- `export GOPATH=$HOME/go`
	- `mkdir -p github.com/sidharthshah`
2. Download code from [code.google.com](https://code.google.com/archive/p/whispering-gophers/source/default/source)
3. Copy code to `cd github.com/sidharthshah`
4. `unzip source-archive.zip`
5. `cd whispering-gophers`
6. `cd hello`
7. `go run hello.go`
8. `go install`
9. `$GOPATH/bin/hello`

## Notes

1. To be able to export to different modules it needs to start with upper case e.g. 'Title' vs 'title'
2. We can chain Reader/Writers, {Sting -> Base 64 Decoder -> Gzip}. Buffer IO is used to speed things up. JSON Encoder is also a Reader
3. There are no exceptions {Panics exists, but only for critical situations}
4. `m := Message{Body: scanner.Text()}` is how you fill in `type`
5. `flag` package provides simple API for parsing command line params {Has nice features including help and default values}
6. Derefercing is done using `*` {Dereferencing Operation is performed to access or manipulate data contained in memory location pointed to by a pointer} [Ref](http://www.c4learn.com/c-programming/c-dereferencing-pointer/)
7. `net` package is used for making TCP/UDP connections
8. `defer c.Close()` is used to close connection
9. `net.Accept` is counter part of `net.Dial`
10. `go` construct to spawn another go routine {Which will make main thread free to listen for incoming connections}. Basically add `go` before a function. No need to join, for go routines to finish. Main thread will automatically close 
11. Idiomatic way `var m Message` of declaring variables without values
12. Goroutines communicate via channels. A channel is a typed conduit that may be synchronous {unbuffered}
	- For un-buffered channels both sender and reciever are blocked till other part is ready. Which is how synchronization happens
13. `go run -race main.go` which will check for race conditions in your code
14. `go test -race` does testing with checking for test condition
15. When doing test using `go test` it will look for all files with *_test.go and execute code within it
16. `RLock` is used only for read locking, no value is getting updated. This gives a little bit more performance 
17. `select` allows to do multiple things at a time