package(default_visibility = ["//visibility:public"])

cc_proto_library(
    name = "analysis",
    deps = ["@io_bazel//src/main/protobuf:analysis_v2_proto"],
)

cc_library(
    name = "bazel",
    srcs = ["bazel.cpp"],
    hdrs = ["bazel.hpp"],
    defines = ["BOOST_PROCESS_USE_STD_FS=1"],
    deps = [
        ":analysis",
        "@boost//:json",
        "@boost//:process",
    ],
)

cc_library(
    name = "compile_commands",
    srcs = ["compile_commands.cpp"],
    hdrs = ["compile_commands.hpp"],
    deps = [
        ":analysis",
        ":replacements",
        "@boost//:io",
        "@boost//:json",
    ],
)

cc_test(
    name = "compile_commands_test",
    srcs = ["compile_commands_test.cpp"],
    deps = [
        ":compile_commands",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_library(
    name = "options",
    srcs = ["options.cpp"],
    hdrs = ["options.hpp"],
    defines = ["BOOST_PROCESS_USE_STD_FS=1"],
    deps = [
        "@boost//:process",
        "@boost//:program_options",
    ],
)

cc_library(
    name = "platform",
    srcs = ["platform.cpp"],
    hdrs = ["platform.hpp"],
    defines = ["BOOST_PROCESS_USE_STD_FS=1"],
    deps = [
        ":replacements",
        "@boost//:process",
    ],
)

cc_library(
    name = "replacements",
    srcs = ["replacements.cpp"],
    hdrs = ["replacements.hpp"],
)

cc_test(
    name = "replacements_test",
    srcs = ["replacements_test.cpp"],
    deps = [
        ":replacements",
        "@com_google_googletest//:gtest_main",
    ],
)
