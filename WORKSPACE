
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "3635797a96c7bfcd0d265dacd722a07335e64d6ded9834af8d3f1b7ba5a25bba",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/4.3.0/rules_nodejs-4.3.0.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories")

node_repositories(package_json = ["//:package.json"])

load("@build_bazel_rules_nodejs//:index.bzl", "yarn_install")

yarn_install(
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

