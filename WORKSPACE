workspace(
    name = "PeripheralInterface",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

"""
Fetch unity and use the file BUILD.unity (residing in this folder) for the build.
We use the prefix new because unity isn't a bazel project, so we need to provide a BUILD file.
More info under https://docs.bazel.build/versions/master/be/workspace.html#new_http_archive
"""

git_repository(
    name = "EmbeddedSystemsBuildScripts",
    branch = "develop",
    remote = "ssh://git@bitbucket.es.uni-due.de:7999/fks/bazel-avr-toolchain-linux.git",
)

load("@EmbeddedSystemsBuildScripts//:avr.bzl", "create_avr_toolchain")

create_avr_toolchain(
    name = "AvrToolchain",
)

http_archive(
    name = "Unity",
    build_file = "@EmbeddedSystemsBuildScripts//:BUILD.Unity",
    strip_prefix = "Unity-master",
    urls = ["https://github.com/ThrowTheSwitch/Unity/archive/master.tar.gz"],
)

http_archive(
    name = "CException",
    build_file = "@EmbeddedSystemsBuildScripts//:BUILD.CException",
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
    build_file = "@EmbeddedSystemsBuildScripts//:BUILD.CMock",
    strip_prefix = "CMock-master",
    urls = ["https://github.com/ThrowTheSwitch/CMock/archive/master.tar.gz"],
)

http_archive(
    name = "LUFA",
    build_file = "@EmbeddedSystemsBuildScripts//:BUILD.LUFA",
    strip_prefix = "lufa-LUFA-170418",
    urls = ["http://fourwalledcubicle.com/files/LUFA/LUFA-170418.zip"],
)

#git_repository(
local_repository(
    name = "EmbeddedUtilities",
    path = "../EmbeddedUtil",
#    commit = "5bfd18c56dc90041662bb532e6c06371a9a4f2d2",
#    remote = "ssh://git@bitbucket.es.uni-due.de:7999/im/embedded-utilities.git",
)

git_repository(
    name = "PeripheralInterface",
    commit = "1e0e60cacdbb9a8dd6871d826951c76cd305f030",
    remote = "ssh://git@bitbucket.es.uni-due.de:7999/im/peripheralinterface.git",
    shallow_since = "1555567164 +0200",
)
