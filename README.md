# Summary of [Golang Talk](https://www.meetup.com/Mumbai-GoLang-Meetup/events/237780164/?comment_table_id=250951560&comment_table_name=reply)

- We will be building P2P chat application called Whisper
- [Slides](https://talks.golang.org/2017/state-of-go.slide#2)
- [A Tour of Go](https://tour.golang.org/welcome/1) is a good reference 
- This code lab is divived into 8 exercises

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