package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_test(
    name = "go_default_test",
    srcs = [
        "github_test.go",
        "status_change_test.go",
    ],
    library = ":go_default_library",
    deps = [
        "//mungegithub/github/testing:go_default_library",
        "//vendor/github.com/google/go-github/github:go_default_library",
    ],
)

go_library(
    name = "go_default_library",
    srcs = [
        "github.go",
        "status_change.go",
        "webhook.go",
    ],
    deps = [
        "//mungegithub/options:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/google/go-github/github:go_default_library",
        "//vendor/github.com/gregjones/httpcache:go_default_library",
        "//vendor/github.com/gregjones/httpcache/diskcache:go_default_library",
        "//vendor/github.com/peterbourgon/diskv:go_default_library",
        "//vendor/golang.org/x/oauth2:go_default_library",
        "//vendor/k8s.io/kubernetes/pkg/util/sets:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//mungegithub/github/testing:all-srcs",
    ],
    tags = ["automanaged"],
)
