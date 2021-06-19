workspace(name = "neuron_delegate")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "org_tensorflow",
    sha256 = "9a0a0dba224c5fbae4c752016ac4fd69602fa841e605d8d5b9d644c3a4c1e5af",
    strip_prefix = "tensorflow-85ea65bfefc79f8e7d8a91ba86d2c3e72586131d",
    urls = [
        "https://github.com/tensorflow/tensorflow/archive/85ea65bfefc79f8e7d8a91ba86d2c3e72586131d.zip",
    ],
)

# Initialize tensorflow workspace.
load("@org_tensorflow//tensorflow:workspace3.bzl", "tf_workspace3")
tf_workspace3()

load("@org_tensorflow//tensorflow:workspace2.bzl", "tf_workspace2")
tf_workspace2()

# Android.
android_sdk_repository(
    name = "androidsdk",
    api_level = 28,
)

android_ndk_repository(
    name = "androidndk",
)

# Specify the minimum required bazel version.
load("@org_tensorflow//tensorflow:version_check.bzl", "check_bazel_version_at_least")

check_bazel_version_at_least("3.1.0")
