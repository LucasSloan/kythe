package(default_visibility = ["//kythe:default_visibility"])

sh_test(
    name = "test_kindex_tool",
    size = "small",
    srcs = [
        "test_kindex_tool.sh",
    ],
    data = [
        "java.kindex_UNIT",
        "java.kindex_cf28b786fa21d0c45156e8011ac809afc454703fa03d767a5aeeed382f902795",
        "//kythe/cxx/tools:kindex_tool",
    ],
)

sh_test(
    name = "test_claim_tool_kindex",
    size = "small",
    srcs = [
        "test_claim_tool_kindex.sh",
    ],
    data = [
        "claim_test.expected",
        "claim_test_1.kindex_UNIT",
        "claim_test_2.kindex_UNIT",
        "//kythe/cxx/tools:kindex_tool",
        "//kythe/cxx/tools:static_claim",
    ],
)

sh_test(
    name = "test_claim_tool_index_pack",
    size = "small",
    srcs = [
        "test_claim_tool_index_pack.sh",
    ],
    data = [
        "claim_test.expected",
        "claim_test_1.kindex_UNIT",
        "claim_test_2.kindex_UNIT",
        "//kythe/cxx/tools:kindex_tool",
        "//kythe/cxx/tools:static_claim",
        "//kythe/go/platform/tools/indexpack",
    ],
)

# TODO(T270): requires declarations generated in pipeline
# sh_test(
#     name = "def_decl_test",
#     srcs = ["def_decl_test.sh"],
#     data = [
#         "def_decl_test.cc",
#         "//kythe/cxx/indexer/cxx:indexer",
#         "//kythe/go/serving/tools:kythe",
#         "//kythe/go/serving/tools:write_tables",
#         "//kythe/go/storage/tools/write_entries",
#     ],
#     tags = ["manual"],  # Currently failing.
# )
