load("@io_bazel_rules_go//go:def.bzl", "go_binary")

package(default_visibility = ["//kythe:default_visibility"])

action_listener(
    name = "print_extra_actions",
    extra_actions = [":printer"],
    mnemonics = [
        "Javac",
        "CppCompile",
        "GoCompile",
    ],
    visibility = ["//visibility:public"],
)

extra_action(
    name = "printer",
    cmd = "$(location :print_extra_action) $(EXTRA_ACTION_FILE)",
    tools = [":print_extra_action"],
)

go_binary(
    name = "print_extra_action",
    srcs = ["print_extra_action.go"],
    deps = [
        "//kythe/go/platform/vfs",
        "//third_party/bazel:extra_actions_base_proto_go",
        "@go_protobuf//:proto",
    ],
)
