load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "rules_proto_grpc",
    urls = ["https://github.com/rules-proto-grpc/rules_proto_grpc/archive/1.0.0.tar.gz"],
    sha256 = "5b9b38a81ebf63c38e7c697d774edbeb3d078623e3ed022ce68bef96f684cfc5",
    strip_prefix = "rules_proto_grpc-1.0.0",
)

load("@rules_proto_grpc//:repositories.bzl", "rules_proto_grpc_toolchains", "rules_proto_grpc_repos", "bazel_gazelle", "io_bazel_rules_go")
rules_proto_grpc_toolchains()
rules_proto_grpc_repos()

io_bazel_rules_go()

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

go_register_toolchains()

bazel_gazelle()

load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")

gazelle_dependencies()

load("@rules_proto_grpc//github.com/grpc-ecosystem/grpc-gateway:repositories.bzl", rules_proto_grpc_gateway_repos="gateway_repos")

rules_proto_grpc_gateway_repos()

load("@grpc_ecosystem_grpc_gateway//:repositories.bzl", "go_repositories")

go_repositories()

load("@rules_proto_grpc//java:repositories.bzl", rules_proto_grpc_java_repos="java_repos")

rules_proto_grpc_java_repos()