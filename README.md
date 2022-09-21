```
aryehh@aryehh ~/Development/docker-bazel
 % bazel query //...                                               
//:base
//:compile
//:image
Loading: 1 packages loaded
aryehh@aryehh ~/Development/docker-bazel
 % bazel run //:image                                              
INFO: Analyzed target //:image (0 packages loaded, 3 targets configured).
INFO: Found 1 target...
ERROR: /usr/local/google/home/aryehh/Development/docker-bazel/BUILD:13:25: Action compile_commit.tar failed: (Exit 1): compile.build failed: error executing command bazel-out/k8-fastbuild-ST-4a519fd6d3e4/bin/compile.build

Use --sandbox_debug to see verbose messages from the sandbox and retain the sandbox build root for debugging
Unable to extract manifest.json, make sure bazel-out/k8-fastbuild-ST-4a519fd6d3e4/bin/base-layer.tar is a valid docker image.
 "filename 'manifest.json' not found"
open /usr/local/google/docker/tmp/docker-import-2679917659/repositories: no such file or directory
Unable to find image 'sh:latest' locally
Error response from daemon: pull access denied for sh, repository does not exist or may require 'docker login': denied: requested access to the resource is denied
Error: No such container: 
"docker rm" requires at least 1 argument.
See 'docker rm --help'.

Usage:  docker rm [OPTIONS] CONTAINER [CONTAINER...]

Remove one or more containers
Target //:image failed to build
Use --verbose_failures to see the command lines of failed build steps.
INFO: Elapsed time: 2.005s, Critical Path: 1.65s
INFO: 3 processes: 3 internal.
FAILED: Build did NOT complete successfully
FAILED: Build did NOT complete successfully
```
