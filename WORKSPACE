load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_file")

# Skylib

http_archive(
    name = "bazel_skylib",
    sha256 = "f7be3474d42aae265405a592bb7da8e171919d74c16f082a5457840f06054728",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-skylib/releases/download/1.2.1/bazel-skylib-1.2.1.tar.gz",
        "https://github.com/bazelbuild/bazel-skylib/releases/download/1.2.1/bazel-skylib-1.2.1.tar.gz",
    ],
)

load("@bazel_skylib//:workspace.bzl", "bazel_skylib_workspace")

bazel_skylib_workspace()

# Docker

http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "b1e80761a8a8243d03ebca8845e9cc1ba6c82ce7c5179ce2b295cd36f7e394bf",
    urls = ["https://github.com/bazelbuild/rules_docker/releases/download/v0.25.0/rules_docker-v0.25.0.tar.gz"],
)

load(
    "@io_bazel_rules_docker//repositories:repositories.bzl",
    container_repositories = "repositories",
)
container_repositories()

load("@io_bazel_rules_docker//repositories:deps.bzl", container_deps = "deps")

container_deps()

# Docker images

load("@io_bazel_rules_docker//container:container.bzl", "container_pull")

container_pull(
    name = "centos",
    digest = "sha256:dead07b4d8ed7e29e98de0f4504d87e8880d4347859d839686a31da35a3b532f", # centos:centos7
    registry = "index.docker.io",
    repository = "centos",
)

# Source

http_file(
    name = "src_archive",
    urls = [
        # Just an example -- in practice, I'll be pulling other sources that can't be compiled with bazel
        "https://github.com/bazelbuild/rules_docker/archive/refs/tags/v0.25.0.zip"
    ],
    sha256 = "21210314056de7183fbe8f4dabb3dcbf47f4dee7b76e2770dcc650c88d5846d6"
)