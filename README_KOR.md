# gRPC 시작에서 운영까지

gRPC 시작에서 운영까지 책의 예제 코드가 제대로 작동하지 않아서
제 환경에 맞춰 작동하게 수정했습니다.

환경
- Java 11
- Gradle 7.4.1
- Go 1.18.3

protoc 설치 후 아래의 명령어로
protoc-gen-go 와 protoc-gen-go-grpc 이 두개도 설치를 진행해야
protoc를 go언어에도 사용이 가능합니다.

```shell
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```

그리고 아래 명령어로 해주셔야 합니다.

```shell
protoc -I=. \
	    --go_out . --go_opt paths=source_relative \
	    --go-grpc_out . --go-grpc_opt paths=source_relative \
	    example/example.proto
```

----
참조
- 원서 예제 코드: https://github.com/grpc-up-and-running/samples/
- 번역 본 예제 코드: https://github.com/switchover/grpc-up-and-running