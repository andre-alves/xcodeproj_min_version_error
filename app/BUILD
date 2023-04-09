load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application")
load("@build_bazel_rules_apple//apple:versioning.bzl", "apple_bundle_version")
load("@build_bazel_rules_swift//swift:swift.bzl", "swift_library")
load("@rules_xcodeproj//xcodeproj:defs.bzl", "top_level_target", "xcodeproj")

IOS_DEPLOYMENT_TARGET = "14.0"

xcodeproj(
    name = "SampleXcodeProj",
    project_name = "Sample",
    build_mode = "xcode",
    tags = ["manual"],
    top_level_targets = [
        top_level_target(":SampleApp", target_environments = ["simulator"]),
    ],
)

ios_application(
    name = "SampleApp",
    app_icons = glob(["Resources/Assets/AppIcon.xcassets/**/*"]),
    bundle_id = "com.test.andre.sampleapp",
    bundle_name = "SampleApp",
    families = [
        "iphone",
        "ipad",
    ],
    infoplists = ["Resources/Info.plist"],
    minimum_os_version = IOS_DEPLOYMENT_TARGET,
    version = ":SampleAppVersion",
    visibility = ["//visibility:public"],
    deps = [
        ":SampleLibrary",
    ],
)

apple_bundle_version(
    name = "SampleAppVersion",
    build_version = "1.2.3.4",
    short_version_string = "1.2.3",
    tags = ["manual"],
)

swift_library(
    name = "SampleLibrary",
    srcs = glob(["Sources/**/*.swift"]),
    module_name = "SampleLibrary",
    tags = ["manual"],
    deps = [
        "//modules/Social:Social",
        "//frameworks:FBSDKShareKit",
    ],
)
