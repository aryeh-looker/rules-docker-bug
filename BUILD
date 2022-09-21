load("@io_bazel_rules_docker//container:container.bzl", "container_image")
load("@io_bazel_rules_docker//docker/util:run.bzl", "container_run_and_commit")

# base image with src archive
container_image(
    name = "base",
    base = "@centos//image",
    files = [
        "@src_archive//file",
    ],
)

container_run_and_commit(
    name = "compile",
    image = ":base",
    commands = [
        "yum -y update",
        "yum -y groupinstall 'Development Tools'",
        "unzip v0.25.0.zip"
        # etc.
    ]
)

container_image(
    name = "image",
    base = ":compile",
    entrypoint = "/bin/bash",
)