load("@build_bazel_rules_apple//apple:apple.bzl", "apple_dynamic_xcframework_import")

apple_dynamic_xcframework_import(
    name = "FBSDKCoreKit",
    visibility = ["//visibility:public"],
    xcframework_imports = glob(["FBSDKCoreKit/XCFrameworks/FBSDKCoreKit.xcframework/**"]),
    deps = [
        ":FBAEMKit",
        ":FBSDKCoreKit_Basics",
    ],
)

apple_dynamic_xcframework_import(
    name = "FBSDKCoreKit_Basics",
    visibility = ["//visibility:public"],
    xcframework_imports = glob(["FBSDKCoreKit_Basics/XCFrameworks/FBSDKCoreKit_Basics.xcframework/**"]),
)

apple_dynamic_xcframework_import(
    name = "FBAEMKit",
    visibility = ["//visibility:public"],
    xcframework_imports = glob(["FBAEMKit/XCFrameworks/FBAEMKit.xcframework/**"]),
    deps = [":FBSDKCoreKit_Basics"],
)

apple_dynamic_xcframework_import(
    name = "FBSDKShareKit",
    visibility = ["//visibility:public"],
    xcframework_imports = glob(["FBSDKShareKit/XCFrameworks/FBSDKShareKit.xcframework/**"]),
    deps = [":FBSDKCoreKit"],
)
