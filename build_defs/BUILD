subinclude("///proto//build_defs/sdk")

proto_build_defs(
    name = "go_proto",
    srcs = ["go.build_defs"],
    proto_languages = {
        "grpc_language": ["go_grpc_language"],
        "proto_language": ["go_proto_language"],
    },
    visibility = ["PUBLIC"],
)
