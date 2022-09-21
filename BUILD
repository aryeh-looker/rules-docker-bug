load("@io_bazel_rules_docker//container:container.bzl", "container_image")
load("@io_bazel_rules_docker//container:container.bzl", "container_layer")
load("@io_bazel_rules_docker//docker/util:run.bzl", "container_run_and_commit")

container_layer(
    name = "src_layer",
    files = [
        "@src_archive//file",
    ],
)

container_image(
    name = "compiler",
    base = "@centos//image",
    layers = [":src_layer"],
)

container_run_and_commit(
    name = "compile",
    image = ":compiler.tar",
    commands = [
        "yum -y update",
        "yum -y groupinstall 'Development Tools'",
        "unzip srcs.zip",
        # etc.
    ]
)

container_image(
    name = "wrapper",
    base = ":compile_commit.tar",
)