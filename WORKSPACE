workspace(name = "io_kythe")

load("//:version.bzl", "check_version")

# Check that the user has a version between our minimum supported version of
# Bazel and our maximum supported version of Bazel.
check_version("0.6.0", "0.7.0")

load("//tools/cpp:clang_configure.bzl", "clang_configure")

clang_configure()

load("//tools/build_rules/config:system.bzl", "cc_system_package")

cc_system_package(
    name = "libuuid",
    default = "/usr/local/opt/ossp-uuid",
    envvar = "UUID_HOME",
    modname = "uuid",
)

new_http_archive(
    name = "org_libmemcached_libmemcached",
    build_file = "third_party/libmemcached.BUILD",
    sha256 = "e22c0bb032fde08f53de9ffbc5a128233041d9f33b5de022c0978a2149885f82",
    strip_prefix = "libmemcached-1.0.18",
    url = "https://launchpad.net/libmemcached/1.0/1.0.18/+download/libmemcached-1.0.18.tar.gz",
)

bind(
    name = "libmemcached",
    actual = "@org_libmemcached_libmemcached//:libmemcached",
)

http_archive(
    name = "boringssl",  # Must match upstream workspace name.
    # Gitiles creates gzip files with an embedded timestamp, so we cannot use
    # sha256 to validate the archives.  We must rely on the commit hash and https.
    # Commits must come from the master-with-bazel branch.
    url = "https://boringssl.googlesource.com/boringssl/+archive/4be3aa87917b20fedc45fa1fc5b6a2f3738612ad.tar.gz",
)

# Make sure to update regularly in accordance with Abseil's principle of live at HEAD
http_archive(
    name = "com_google_absl",
    strip_prefix = "abseil-cpp-da336a84e9c1f86409b21996164ae9602b37f9ca",
    url = "https://github.com/abseil/abseil-cpp/archive/da336a84e9c1f86409b21996164ae9602b37f9ca.zip",
)

http_archive(
    name = "com_google_googletest",
    sha256 = "89cebb92b9a7eb32c53e180ccc0db8f677c3e838883c5fbd07e6412d7e1f12c7",
    strip_prefix = "googletest-d175c8bf823e709d570772b038757fadf63bc632",
    url = "https://github.com/google/googletest/archive/d175c8bf823e709d570772b038757fadf63bc632.zip",
)

http_archive(
    name = "com_github_gflags_gflags",
    sha256 = "94ad0467a0de3331de86216cbc05636051be274bf2160f6e86f07345213ba45b",
    strip_prefix = "gflags-77592648e3f3be87d6c7123eb81cbad75f9aef5a",
    url = "https://github.com/gflags/gflags/archive/77592648e3f3be87d6c7123eb81cbad75f9aef5a.zip",
)

http_archive(
    name = "com_googlesource_code_re2",
    # Gitiles creates gzip files with an embedded timestamp, so we cannot use
    # sha256 to validate the archives.  We must rely on the commit hash and https.
    url = "https://code.googlesource.com/re2/+archive/2c220e7df3c10d42d74cb66290ec89116bb5e6be.tar.gz",
)

new_http_archive(
    name = "com_github_google_glog",
    build_file = "third_party/googlelog.BUILD",
    sha256 = "ce61883437240d650be724043e8b3c67e257690f876ca9fd53ace2a791cfea6c",
    strip_prefix = "glog-bac8811710c77ac3718be1c4801f43d37c1aea46",
    url = "https://github.com/google/glog/archive/bac8811710c77ac3718be1c4801f43d37c1aea46.zip",
)

maven_jar(
    name = "com_google_code_gson_gson",
    artifact = "com.google.code.gson:gson:2.8.2",
    sha1 = "3edcfe49d2c6053a70a2a47e4e1c2f94998a49cf",
)

maven_jar(
    name = "com_google_guava_guava",
    artifact = "com.google.guava:guava:23.3-jre",
    sha1 = "9124c2675a9de3ba953f66d62339cf62f8e1a143",
)

maven_jar(
    name = "junit_junit",
    artifact = "junit:junit:4.12",
    sha1 = "2973d150c0dc1fefe998f834810d68f278ea58ec",
)

maven_jar(
    name = "com_google_re2j_re2j",
    artifact = "com.google.re2j:re2j:1.1",
    sha1 = "d716952ab58aa4369ea15126505a36544d50a333",
)

maven_jar(
    name = "com_beust_jcommander",
    artifact = "com.beust:jcommander:1.72",
    sha1 = "6375e521c1e11d6563d4f25a07ce124ccf8cd171",
)

maven_jar(
    name = "com_google_truth_truth",
    artifact = "com.google.truth:truth:0.36",
    sha1 = "7485219d2c1d341097a19382c02bde07e69ff5d2",
)

maven_jar(
    name = "com_google_code_findbugs_jsr305",
    artifact = "com.google.code.findbugs:jsr305:3.0.1",
    sha1 = "f7be08ec23c21485b9b5a1cf1654c2ec8c58168d",
)

maven_jar(
    name = "com_google_auto_value_auto_value",
    artifact = "com.google.auto.value:auto-value:1.5.2",
    sha1 = "1b94ab7ec707e2220a0d1a7517488d1843236345",
)

maven_jar(
    name = "com_google_auto_service_auto_service",
    artifact = "com.google.auto.service:auto-service:1.0-rc3",
    sha1 = "35c5d43b0332b8f94d473f9fee5fb1d74b5e0056",
)

maven_jar(
    name = "com_google_auto_auto_common",
    artifact = "com.google.auto:auto-common:0.8",
    sha1 = "c6f7af0e57b9d69d81b05434ef9f3c5610d498c4",
)

http_archive(
    name = "com_google_dagger",
    # TODO(ronshapiro): Switch back to a versioned release of dagger
    strip_prefix = "dagger-6863e7ef018a3f483ed76092cd41d83daf0b45e5",
    url = "https://github.com/google/dagger/archive/6863e7ef018a3f483ed76092cd41d83daf0b45e5.zip",
)

maven_jar(
    name = "javax_annotation_jsr250_api",
    artifact = "javax.annotation:jsr250-api:1.0",
    sha1 = "5025422767732a1ab45d93abfea846513d742dcf",
)

maven_jar(
    name = "javax_inject_javax_inject",
    artifact = "javax.inject:javax.inject:1",
    sha1 = "6975da39a7040257bd51d21a231b76c915872d38",
)

maven_jar(
    name = "com_google_errorprone_javac",
    artifact = "com.google.errorprone:javac-shaded:9-dev-r4023-3",
    sha1 = "72b688efd290280a0afde5f9892b0fde6f362d1d",
)

maven_jar(
    name = "com_google_googlejavaformat_google_java_format",
    artifact = "com.google.googlejavaformat:google-java-format:1.4",
    sha1 = "c2f8925850e17caa6da0ed1891a9e9de9414c062",
)

maven_jar(
    name = "com_google_errorprone_error_prone_annotations",
    artifact = "com.google.errorprone:error_prone_annotations:2.0.12",
    sha1 = "8530d22d4ae8419e799d5a5234e0d2c0dcf15d4b",
)

maven_jar(
    name = "com_squareup_javapoet",
    artifact = "com.squareup:javapoet:1.8.0",
    sha1 = "e858dc62ef484048540d27d36f3ec2177a3fa9b1",
)

maven_jar(
    name = "com_google_common_html_types",
    artifact = "com.google.common.html.types:types:1.0.7",
    sha1 = "7d4afac9f631a2c1adecc21350a4e88241185eb4",
)

#TODO(T276): Update Go rules to version 0.5.5 or later,
#  along with external repositories.
git_repository(
    name = "io_bazel_rules_go",
    remote = "https://github.com/bazelbuild/rules_go.git",
    tag = "0.4.3",
)

load("@io_bazel_rules_go//go:def.bzl", "go_repositories")

go_repositories(go_version = "1.8.1")

new_git_repository(
    name = "go_grpc",
    build_file = "third_party/go/grpc.BUILD",
    commit = "61d37c5d657a47e4404fd6823bd598341a2595de",
    remote = "https://github.com/grpc/grpc-go.git",
)

new_git_repository(
    name = "go_genproto",
    build_file = "third_party/go/genproto.BUILD",
    commit = "f676e0f3ac6395ff1a529ae59a6670878a8371a6",
    remote = "https://github.com/google/go-genproto.git",
)

new_git_repository(
    name = "go_errors",
    build_file = "third_party/go/errors.BUILD",
    commit = "ff09b135c25aae272398c51a07235b90a75aa4f0",
    remote = "https://github.com/pkg/errors.git",
)

new_git_repository(
    name = "go_gogo_protobuf",
    build_file = "third_party/go/gogo_protobuf.BUILD",
    commit = "f9114dace7bd920b32f943b3c73fafbcbab2bf31",
    remote = "https://github.com/gogo/protobuf.git",
)

new_git_repository(
    name = "go_x_net",
    build_file = "third_party/go/x_net.BUILD",
    commit = "de35ec43e7a9aabd6a9c54d2898220ea7e44de7d",
    remote = "https://github.com/golang/net.git",
)

new_git_repository(
    name = "go_x_text",
    build_file = "third_party/go/x_text.BUILD",
    commit = "d5d7737684e596dbabf914ecf946d2783f35bdc2",
    remote = "https://github.com/golang/text.git",
)

new_git_repository(
    name = "go_x_tools",
    build_file = "third_party/go/x_tools.BUILD",
    commit = "5682db0e919ed9cfc6f52ac32e170511a106eb3b",
    remote = "https://go.googlesource.com/tools",
)

new_git_repository(
    name = "go_subcommands",
    build_file = "third_party/go/subcommands.BUILD",
    commit = "ce3d4cfc062faac7115d44e5befec8b5a08c3faa",
    remote = "https://github.com/google/subcommands.git",
)

new_git_repository(
    name = "go_shell",
    build_file = "third_party/go/shell.BUILD",
    commit = "3dcd505a7ca5845388111724cc2e094581e92cc6",
    remote = "https://bitbucket.org/creachadair/shell.git",
)

new_git_repository(
    name = "go_stringset",
    build_file = "third_party/go/stringset.BUILD",
    commit = "a3e24d67df15a89cae7f6b10b64ecb2051045bb7",
    remote = "https://bitbucket.org/creachadair/stringset.git",
)

new_git_repository(
    name = "go_diff",
    build_file = "third_party/go/diff.BUILD",
    commit = "ec7fdbb58eb3e300c8595ad5ac74a5aa50019cc7",
    remote = "https://github.com/sergi/go-diff.git",
)

new_git_repository(
    name = "go_uuid",
    build_file = "third_party/go/uuid.BUILD",
    commit = "c55201b036063326c5b1b89ccfe45a184973d073",
    remote = "https://github.com/pborman/uuid.git",
)

new_git_repository(
    name = "go_snappy",
    build_file = "third_party/go/snappy.BUILD",
    commit = "d9eb7a3d35ec988b8585d4a0068e462c27d28380",
    remote = "https://github.com/golang/snappy.git",
)

new_git_repository(
    name = "go_protobuf",
    build_file = "third_party/go/protobuf.BUILD",
    commit = "8ee79997227bf9b34611aee7946ae64735e6fd93",
    remote = "https://github.com/golang/protobuf.git",
)

new_git_repository(
    name = "go_langserver",
    build_file = "third_party/go/langserver.BUILD",
    commit = "d354d3b84b3a1ef4a38679290e4fb4d32ffe3567",
    remote = "https://github.com/sourcegraph/go-langserver.git",
)

new_git_repository(
    name = "go_jsonrpc2",
    build_file = "third_party/go/jsonrpc2.BUILD",
    commit = "3a7c446248199a2abc2dff3cf97bb4f3c0028e5f",
    remote = "https://github.com/sourcegraph/jsonrpc2.git",
)

new_git_repository(
    name = "go_levigo",
    build_file = "third_party/go/levigo.BUILD",
    commit = "1ddad808d437abb2b8a55a950ec2616caa88969b",
    remote = "https://github.com/jmhodges/levigo.git",
)

new_git_repository(
    name = "go_sync",
    build_file = "third_party/go/sync.BUILD",
    commit = "f52d1811a62927559de87708c8913c1650ce4f26",
    remote = "https://github.com/golang/sync",
)
