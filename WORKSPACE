"""
The location of this file (even when empty) specifies the project root
for more info see https://docs.bazel.build/versions/master/build-ref.html
"""

"""
set the global repository name, this function can only be called from this file
https://docs.bazel.build/versions/master/be/functions.html#workspace
"""

workspace(
    name = "PeripheralInterface",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@//:department.bzl", "create_avr_toolchain")

http_archive(
    name = "Unity",
    build_file = "@//:BUILD.Unity",
    strip_prefix = "Unity-master",
    urls = ["https://github.com/ThrowTheSwitch/Unity/archive/master.tar.gz"],
)

http_archive(
    name = "CException",
    build_file = "@//:BUILD.CException",
    strip_prefix = "CException-master",
    urls = ["https://github.com/ThrowTheSwitch/CException/archive/master.tar.gz"],
)

http_archive(
    name = "UnityPlugin",
    strip_prefix = "BazelUnityPlugin-develop",
    urls = ["https://github.com/glencoe/BazelUnityPlugin/archive/develop.tar.gz"],
)

http_archive(
    name = "CMock",
    build_file = "@//:BUILD.CMock",
    strip_prefix = "CMock-master",
    urls = ["https://github.com/ThrowTheSwitch/CMock/archive/master.tar.gz"],
)

git_repository(
    name = "EmbeddedUtilities",
    commit = "5bfd18c56dc90041662bb532e6c06371a9a4f2d2",
    remote = "ssh://git@bitbucket.es.uni-due.de:7999/im/embedded-utilities.git",
)

local_repository(
    name = "AVR_Toolchain",
    path = "../bazel-avr-toolchain-linux",
)

create_avr_toolchain(
    name = "Toolchain",
    avr_gcc = "",
)
