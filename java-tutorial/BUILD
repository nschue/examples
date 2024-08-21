load("@rules_java//java:defs.bzl", "java_binary")

package(default_visibility = ["//visibility:public"])

java_binary(
    name = "ProjectRunner",
    srcs = ["src/main/java/com/example/ProjectRunner.java"],
    main_class = "com.example.ProjectRunner",
    deps = [":greeter"],
)

java_library(
    name = "greeter",
    srcs = ["src/main/java/com/example/Greeting.java"],
    deps = ["@maven//:org_apache_commons_commons_lang3",],
    visibility = ["//src/main/java/com/example/cmdline:__pkg__"],
)

# BUILD
load("@rules_proto//proto:defs.bzl", "proto_library")
load("@rules_java//java:defs.bzl", "java_library")

proto_library(
    name = "helloworld_proto",
    srcs = ["helloworld.proto"],
    deps = [],
)

java_library(
    name = "helloworld_java",
    srcs = [":helloworld_proto"],
    deps = [
        "@rules_proto//proto:java_proto_library",
    ],
)