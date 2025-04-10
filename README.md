
# CollectorProto

Protocol definitions and generated Go files for the **UpOrDownDetector** data controller microservice.

This repository contains `.proto` files for gRPC communication between microservices, along with generated Go code.

## Structure

- `protos/` – source `.proto` files  
- `gen/go/` – generated Go code (`.pb.go`, `.pb_grpc.go`)  
- `go.mod` – Go module for usage in other services  

## Usage

### Code Generation

To regenerate Go code from `.proto` files:

```bash
protoc --go_out=gen/go --go-grpc_out=gen/go protos/collector.proto
```

Make sure you have the required tools installed:

```bash
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```

### Importing the Module

To use the generated types and services in another Go project:

1. Add the module to your `go.mod` (replace with the actual repo path):

```bash
go get github.com/Skvidich/CollectorProto@latest
```

2. Import in your code:

```go
import pb "github.com/Skvidich/CollectorProto/gen/go"
```

