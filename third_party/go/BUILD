subinclude("///go//build_defs:go")

go_toolchain(
    name = "toolchain",
    version = "1.22.3",
)

go_module(
    name = "go-spew",
    install = ["spew"],
    module = "github.com/davecgh/go-spew",
    version = "v1.1.0",
    visibility = ["PUBLIC"],
)

go_module(
    name = "go-difflib",
    install = ["difflib"],
    module = "github.com/pmezard/go-difflib",
    version = "v1.0.0",
    visibility = ["PUBLIC"],
)

go_module(
    name = "yaml.v3",
    module = "gopkg.in/yaml.v3",
    version = "v3.0.0-20200313102051-9f266ea9e77c",
    visibility = ["PUBLIC"],
)

go_module(
    name = "testify",
    install = [
        ".",
        "assert",
        "http",
        "mock",
        "require",
        "suite",
    ],
    module = "github.com/stretchr/testify",
    version = "v1.7.0",
    visibility = ["PUBLIC"],
    deps = [
        ":go-difflib",
        ":go-spew",
        ":objx",
        ":yaml.v3",
    ],
)

go_module(
    name = "objx",
    module = "github.com/stretchr/objx",
    version = "v0.1.0",
    visibility = ["PUBLIC"],
)

go_module(
    name = "text",
    install = [
        "secure/bidirule",
        "transform",
        "unicode/bidi",
        "unicode/norm",
    ],
    module = "golang.org/x/text",
    version = "v0.3.0",
    visibility = ["PUBLIC"],
)

go_module(
    name = "protobuf",
    exported_deps = [":google.golang.org.protobuf"],
    install = [
        "proto",
        "ptypes",
        "ptypes/any",
        "ptypes/duration",
        "ptypes/timestamp",
    ],
    module = "github.com/golang/protobuf",
    version = "v1.4.3",
    visibility = ["PUBLIC"],
)

go_module(
    name = "grpc",
    install = [
        ".",
        "attributes",
        "backoff",
        "balancer",
        "balancer/base",
        "balancer/grpclb/state",
        "balancer/roundrobin",
        "binarylog/grpc_binarylog_v1",
        "codes",
        "connectivity",
        "credentials",
        "encoding",
        "encoding/proto",
        "grpclog",
        "internal",
        "internal/backoff",
        "internal/balancerload",
        "internal/binarylog",
        "internal/buffer",
        "internal/channelz",
        "internal/credentials",
        "internal/envconfig",
        "internal/grpclog",
        "internal/grpcrand",
        "internal/grpcsync",
        "internal/grpcutil",
        "internal/metadata",
        "internal/resolver",
        "internal/resolver/dns",
        "internal/resolver/passthrough",
        "internal/resolver/unix",
        "internal/serviceconfig",
        "internal/status",
        "internal/syscall",
        "internal/transport",
        "internal/transport/networktype",
        "internal/xds/env",
        "keepalive",
        "metadata",
        "peer",
        "resolver",
        "serviceconfig",
        "stats",
        "status",
        "tap",
    ],
    module = "google.golang.org/grpc",
    version = "v1.42.0",
    visibility = ["PUBLIC"],
    deps = [
        ":genproto",
        ":google.golang.org.protobuf",
        ":net",
        ":protobuf",
        ":sys",
    ],
)

go_mod_download(
    name = "protobuf_dl",
    module = "google.golang.org/protobuf",
    version = "v1.27.1",
)

go_module(
    name = "google.golang.org.protobuf",
    download = ":protobuf_dl",
    install = [
        "cmd/protoc-gen-go/internal_gengo",
        "compiler/protogen",
        "encoding/prototext",
        "encoding/protowire",
        "internal/...",
        "proto",
        "reflect/protodesc",
        "reflect/protoreflect",
        "reflect/protoregistry",
        "runtime/protoiface",
        "runtime/protoimpl",
        "types/descriptorpb",
        "types/known/anypb",
        "types/known/durationpb",
        "types/known/timestamppb",
        "types/pluginpb",
    ],
    module = "google.golang.org/protobuf",
)

go_module(
    name = "protoc-gen-go-grpc",
    binary = True,
    module = "google.golang.org/grpc/cmd/protoc-gen-go-grpc",
    version = "v1.1.0",
    visibility = ["PUBLIC"],
    deps = [":google.golang.org.protobuf"],
)

go_module(
    name = "protoc-gen-go",
    binary = True,
    download = ":protobuf_dl",
    install = ["cmd/protoc-gen-go"],
    module = "google.golang.org/protobuf",
    visibility = ["PUBLIC"],
    deps = [":google.golang.org.protobuf"],
)

go_module(
    name = "net",
    install = [
        "http/httpguts",
        "http2",
        "http2/hpack",
        "idna",
        "internal/timeseries",
        "trace",
    ],
    module = "golang.org/x/net",
    version = "v0.0.0-20200822124328-c89045814202",
    visibility = ["PUBLIC"],
    deps = [":text"],
)

go_module(
    name = "sys",
    install = ["..."],
    module = "golang.org/x/sys",
    version = "v0.0.0-20220315194320-039c03cc5b86",
    visibility = ["PUBLIC"],
)

go_module(
    name = "genproto",
    install = ["googleapis/rpc/status"],
    module = "google.golang.org/genproto",
    version = "v0.0.0-20200526211855-cb27e3aa2013",
    visibility = ["PUBLIC"],
    deps = [
        ":google.golang.org.protobuf",
        ":protobuf",
    ],
)

go_module(
    name = "go-cmp",
    install = [
        "cmp",
        "cmp/cmpopts",
        "cmp/internal/diff",
        "cmp/internal/flags",
        "cmp/internal/function",
        "cmp/internal/testprotos",
        "cmp/internal/teststructs",
        "cmp/internal/teststructs/foo1",
        "cmp/internal/teststructs/foo2",
        "cmp/internal/value",
    ],
    module = "github.com/google/go-cmp",
    version = "v0.5.6",
    visibility = ["PUBLIC"],
)
