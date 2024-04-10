# Poker

[![GoDoc](https://godoc.org/github.com/chehsunliu/poker?status.svg)](https://godoc.org/github.com/chehsunliu/poker)

Poker is ported from the Python library [worldveil/deuces](https://github.com/worldveil/deuces).

## Installation

Use `go get` to install Poker:

```sh
$ go get github.com/forrest321/pokerEval
```

## Usage

Support 5-, 6-, and 7-card evalutions:

```go
package main

import (
	"fmt"

	"github.com/forrest321/pokerEval"
)

func main() {
	deck := poker.NewDeck()
	hand := deck.Draw(7)
	fmt.Println(hand)

	rank := poker.Evaluate(hand)
	fmt.Println(rank)
	fmt.Println(poker.RankString(rank))
}
```

```sh
$ go run ./main.go
[Kd 4h Qh 3s 8s 5h Jd]
6695
High Card

$ go run ./main.go
[4c Qh Ad 9c 9s 3h 4d]
3062
Two Pair

$ go run ./main.go
[Jh Qd Kd Qs 7d As Qh]
1742
Three of a Kind
```
