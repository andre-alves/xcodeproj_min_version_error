# Repro 

This sample reproduces an error when the project has a module with the same name as one present by Apple.

In this example, we have a module named `Social`, and we also have `FBSDKShareKit.xcframework` which links against the [Social framework from Apple](https://developer.apple.com/documentation/social) (you can check the .swiftinterface to see the import).


Building w/ Bazel works, but building w/ Xcode doesn't. The background indexing is also broken.

### Steps

```
bazel run //app:SampleXcodeProj
open app/Sample.xcodeproj
```

Try to build `SampleApp` scheme, should get an error.

### Environment

- Xcode 14.1
- Bazel 6.1.1
- rules_xcodproj 1.3.3
