load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "doc.go",
        "merge.go",
        "merge_visitor.go",
        "replace_visitor.go",
        "retain_keys_visitor.go",
        "strategic_visitor.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubectl/apply/strategy",
    visibility = ["//visibility:public"],
    deps = ["//pkg/kubectl/apply:go_default_library"],
)

go_test(
    name = "go_default_xtest",
    srcs = [
        "merge_map_list_test.go",
        "merge_map_test.go",
        "merge_primitive_list_test.go",
        "merge_primitive_test.go",
        "replace_map_list_test.go",
        "replace_map_test.go",
        "replace_primitive_list_test.go",
        "retain_keys_test.go",
        "suite_test.go",
        "utils_test.go",
    ],
    data = [
        ":swagger-spec",
        "//api/openapi-spec:swagger-spec",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubectl/apply/strategy_test",
    deps = [
        ":go_default_library",
        "//pkg/kubectl/apply:go_default_library",
        "//pkg/kubectl/apply/parse:go_default_library",
        "//pkg/kubectl/cmd/util/openapi:go_default_library",
        "//pkg/kubectl/cmd/util/openapi/testing:go_default_library",
        "//vendor/github.com/ghodss/yaml:go_default_library",
        "//vendor/github.com/onsi/ginkgo:go_default_library",
        "//vendor/github.com/onsi/ginkgo/config:go_default_library",
        "//vendor/github.com/onsi/ginkgo/types:go_default_library",
        "//vendor/github.com/onsi/gomega:go_default_library",
        "//vendor/k8s.io/apimachinery/pkg/util/diff:go_default_library",
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
    visibility = ["//visibility:public"],
)

filegroup(
    name = "swagger-spec",
    srcs = glob([
        "**/*.json",
    ]),
)
