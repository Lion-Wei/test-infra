package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = [
        "plank_test.go",
        "report_test.go",
    ],
    library = ":go_default_library",
    deps = [
        "//prow/config:go_default_library",
        "//prow/github:go_default_library",
        "//prow/jenkins:go_default_library",
        "//prow/kube:go_default_library",
    ],
)

go_library(
    name = "go_default_library",
    srcs = [
        "controller.go",
        "plank.go",
        "report.go",
    ],
    deps = [
        "//prow/config:go_default_library",
        "//prow/github:go_default_library",
        "//prow/jenkins:go_default_library",
        "//prow/kube:go_default_library",
        "//prow/plugins:go_default_library",
        "//vendor/github.com/Sirupsen/logrus:go_default_library",
        "//vendor/github.com/bwmarrin/snowflake:go_default_library",
        "//vendor/github.com/satori/go.uuid:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)
