# Golang proto rules
Golang protobuf definitions for the [Proto](https://github.com/please-build/proto-rules) plugin, for the 
[Please](https://please.build) build system.

# Basic usage
First add the proto plugin and this plugin to your project:
```python
# BUILD
plugin_repo(
    name = "proto",
    revision = "<Some git tag, commit, or other reference>",
)

plugin_repo(
    name = "go-proto",
    revision = "<Some git tag, commit, or other reference>",
)
```

Then add the go-proto to the list of language definitions:
```ini
[Plugin "proto"]
LanguageDef = ///go_proto//build_defs:go
```

You'll then need to add the [protobuf sdk](https://github.com/golang/protobuf), as well as the 
[gRPC sdk](https://google.golang.org/grpc) if you want to use `grpc_library()`. You can copy the `go_module()` rules 
from `third_party/go/BUILD` in this repo to get started. 

You can then use `proto_library()` or `grpc_library()` to generate go code for your .proto files: 

```python
grpc_library(
    name = "proto",
    srcs = ["service.proto"],
    visibility = ["//service/..."]
)
```

```python
go_binary(
    name = "service",
    srcs = ["main.go"],
    # This is the proto above
    deps = ["//service/proto:proto"], 
)
```

See the [Proto](https://github.com/please-build/proto-rules) plugin for more information on these rules. 

# Configuration
This plugin can be configured via the plugins section as follows:
```python
[Plugin "go-proto"]
SomeConfig = some-value
```
