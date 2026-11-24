# banking 
[![GoDoc](http://img.shields.io/badge/go-documentation-blue.svg?style=flat-square)](https://pkg.go.dev/github.com/gamezop/banking) 
[![Build Status](https://github.com/gamezop/banking/actions/workflows/go.yml/badge.svg)](https://github.com/gamezop/banking/actions/workflows/go.yml)
[![Go Report Card](https://goreportcard.com/badge/github.com/gamezop/banking)](https://goreportcard.com/report/github.com/gamezop/banking)

Banking library for Go.

## Install

```bash
go get github.com/gamezop/banking
```

## Docs

http://godoc.org/github.com/gamezop/banking

## Iban

```go
package main

import (
    "fmt"
    "log"

    "github.com/gamezop/banking/iban"
)

var (
    testIban = iban.MustParse("BE68539007547034")
)

func main() {
    ibn, err := iban.Parse("BE68539007547034")
    if err != nil {
        log.Fatal(err)
    }

    fmt.Println(ibn.BankCode())
    fmt.Println(ibn.AccountNumber())

    err = iban.Validate("BE68539007547034")
    if err != nil {
        log.Fatal(err)
    }
}
```

## Swift

```go
package main

import (
    "fmt"
    "log"

    "github.com/gamezop/banking/swift"
)

var (
    testSwift = swift.MustParse("DEUTDEFF500")
)

func main() {
    swft, err := swift.Parse("DEUTDEFF500")
    if err != nil {
        log.Fatal(err)
    }

    fmt.Println(swft.BankCode())
    fmt.Println(swft.CountryCode())

    err = swift.Validate("DEUTDEFF500")
    if err != nil {
        log.Fatal(err)
    }
}
```