workspace(name = "bazel-compile-commands")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

_RULES_BOOST_COMMIT = "33461a3c666af36d7a080e4fd6f554725df44132"

http_archive(
    name = "com_github_nelhage_rules_boost",
    sha256 = "1198cb810d18d2a86abbd4c3d71665375e2c6a2ba4044b4f9d7b2f28e6ed898e",
    strip_prefix = "rules_boost-%s" % _RULES_BOOST_COMMIT,
    urls = [
        "https://github.com/nelhage/rules_boost/archive/%s.tar.gz" % _RULES_BOOST_COMMIT,
    ],
)

load("@com_github_nelhage_rules_boost//:boost/boost.bzl", "boost_deps")

boost_deps()

# GoogleTest/GoogleMock framework. Used by most unit-tests.
http_archive(
    name = "com_google_googletest",
    sha256 = "81964fe578e9bd7c94dfdb09c8e4d6e6759e19967e397dbea48d1c10e45d0df2",
    strip_prefix = "googletest-release-1.12.1",
    urls = ["https://github.com/google/googletest/archive/refs/tags/release-1.12.1.tar.gz"],
)

http_archive(
    name = "rules_pkg",
    sha256 = "8f9ee2dc10c1ae514ee599a8b42ed99fa262b757058f65ad3c384289ff70c4b8",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_pkg/releases/download/0.9.1/rules_pkg-0.9.1.tar.gz",
        "https://github.com/bazelbuild/rules_pkg/releases/download/0.9.1/rules_pkg-0.9.1.tar.gz",
    ],
)

load("@rules_pkg//:deps.bzl", "rules_pkg_dependencies")

rules_pkg_dependencies()

http_archive(
    name = "mgred_rules_pandoc",
    sha256 = "0ee76dc7403d40de7946e6b884f3e868e72f2d7ba172edfc828bfb50fd5baf04",
    strip_prefix = "rules_pandoc-0.2.0",
    url = "https://github.com/mgred/rules_pandoc/releases/download/v0.2.0/rules_pandoc-v0.2.0.tar.gz",
)

load("@mgred_rules_pandoc//pandoc:repositories.bzl", "LATEST_PANDOC_VERSION", "pandoc_register_toolchains", "rules_pandoc_dependencies")

rules_pandoc_dependencies()

pandoc_register_toolchains(
    name = "pandoc3_1",
    pandoc_version = LATEST_PANDOC_VERSION,
)
