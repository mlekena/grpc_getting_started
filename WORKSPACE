##### Protobuf Rules for Bazel
##### See https://github.com/bazelbuild/rules_proto

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive", "http_file")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
git_repository(
    name = "rules_proto",
    # commit = "cfdc2fa31879c0aebe31ce7702b1a9c8a4be02d2", #Working commit
    commit = "f7a30f6f80006b591fa7c437fe5a951eb10bcbcf", # Latest commit working
    remote = "https://github.com/bazelbuild/rules_proto.git",
)
load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")
rules_proto_dependencies()
rules_proto_toolchains()

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

##### gRPC Rules for Bazel
##### See https://github.com/grpc/grpc/blob/master/src/cpp/README.md#make
http_archive(
    name = "com_github_grpc_grpc",
    urls = [
        "https://github.com/grpc/grpc/archive/54dc182082db941aa67c7c3f93ad858c99a16d7d.tar.gz",
    ],
    strip_prefix = "grpc-54dc182082db941aa67c7c3f93ad858c99a16d7d",
)
load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps")
grpc_deps()

# Not mentioned in official docs... mentioned here https://github.com/grpc/grpc/issues/20511

load("@com_github_grpc_grpc//bazel:grpc_extra_deps.bzl", "grpc_extra_deps")
grpc_extra_deps()
