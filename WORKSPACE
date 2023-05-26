load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "dd926a88a564a9246713a9c00b35315f54cbd46b31a26d5d8fb264c07045f05d",
    url = "https://github.com/bazelbuild/rules_go/releases/download/v0.38.1/rules_go-v0.38.1.zip",
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "ecba0f04f96b4960a5b250c8e8eeec42281035970aa8852dda73098274d14a1d",
    url = "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.29.0/bazel-gazelle-v0.29.0.tar.gz",
)

http_archive(
    name = "com_google_protobuf",
    strip_prefix = "protobuf-22.0",
    sha256 = "782160a6eae4bddfa4061ff5f7dcf04c9ed1494a0f0c6408b4af6b4a31ab9876",
    urls = [
        "https://github.com/protocolbuffers/protobuf/archive/v22.0.tar.gz",
    ],
)

http_archive(
    name = "com_google_googletest",
    strip_prefix = "googletest-1.13.0",
    sha256 = "ad7fdba11ea011c1d925b3289cf4af2c66a352e18d4c7264392fead75e919363",
    urls = [
        "https://github.com/google/googletest/archive/v1.13.0.tar.gz",
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")
load("//:deps.bzl", "go_dependencies")
load("//toolchains:toolchains.bzl", "register_gaia_toolchains")
load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

register_gaia_toolchains()

# gazelle:repository_macro deps.bzl%go_dependencies
go_dependencies()

go_rules_dependencies()

go_register_toolchains(version = "1.20.1")

gazelle_dependencies()
