# gRPC Up & Running

The example code in the gRPC Up & Running book is not working properly
I modified it to work according to my environment

environment
- Java 11
- Gradle 7.4.1
- Go 1.18.3

After installing protoc, use the following command:
You need to install both protoc-gen-go and protoc-gen-go-grpc
You can also use protoc in the go language.

```shell
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```

And you have to do it with the command below.

```shell
protoc -I=. \
	    --go_out . --go_opt paths=source_relative \
	    --go-grpc_out . --go-grpc_opt paths=source_relative \
	    example/example.proto
```

----
Reference
- https://github.com/grpc-up-and-running/samples/