# Komproto

Komproto is a **proto-bank** which storing all the required `.proto` files and its generated code in single module.

### Generated Code Guide

Based on official docs [**Protobuf**](https://protobuf.dev/reference), here are summarize how to generate proto into specified language.

1. **Golang** ([docs](https://protobuf.dev/reference/go/go-generated))

#### Prerequisites

Before jump over to generate proto into go, these **must** be configured on your machine.

a. installed protobuf-compiler (**protoc**)

Installation example in linux debian or ubuntu

```sh
$ apt install protobuf-compiler
```

b. installed required plugin to generate go code using go toolchain

```sh
$ go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
```

#### Generate Code

Here commonly how to generate proto file into go code.

```sh
protoc --proto_path=IMPORT_PATH --go_out=DST_DIR --go_opt=paths=source_relative path/to/file.proto
```

Flag `proto_path` specifies a directory in which to look for .proto files when resolving import directives. If omitted, the current directory is used. `I=IMPORT_PATH` can be used as a short form of `proto_path`.

Flag `--go_out` generates Go code in DST_DIR.

If the `paths=source_relative` flag is specified, the output file is placed in the same relative directory as the input file. For example, an input file `protos/buzz.proto` results in an output file at `protos/buzz.pb.go`.

2. **Coming Soon**

### Documentation

For further read, you can visit the docs [**Proto3 Guide**](https://protobuf.dev/programming-guides/proto3/), [**Style Guide**](https://protobuf.dev/programming-guides/style/), [**Reference Guide**](https://protobuf.dev/reference/).
