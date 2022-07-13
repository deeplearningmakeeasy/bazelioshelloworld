# load ios application rule
load("@build_bazel_rules_apple//apple:ios.bzl", "ios_application")

# load build in objc_library rule 
load("@rules_cc//cc:defs.bzl", "objc_library")

objc_library(
    name = "BazelHelloworldObjC_classes",
    srcs = [
         "BazelHelloworldObjC/AppDelegate.m",
         "BazelHelloworldObjC/SceneDelegate.m",
         "BazelHelloworldObjC/ViewController.m",
         "BazelHelloworldObjC/main.m",
         
    ],
    hdrs = glob(["BazelHelloworldObjC/*.h"]),
    data = [
    		"BazelHelloworldObjC/Base.lproj/Main.storyboard",
    		"BazelHelloworldObjC/Base.lproj/LaunchScreen.storyboard",
    ],
)

# Use ios application rule
ios_application(
    name = "BazelHelloworldObjCApp",
    bundle_id = "<com.domain.appBundleID>",
    families = [
        "iphone",
        "ipad",
    ],
    minimum_os_version = "13.0",
    infoplists = [":BazelHelloworldObjC/Info.plist"],
    #Must have launch_storyboard, otherwise UI goes funny
    launch_storyboard = "BazelHelloworldObjC/Base.lproj/LaunchScreen.storyboard",
    provisioning_profile = "<Your App Provisioning Profile>.mobileprovision",
    visibility = ["//visibility:public"],
    deps = [":BazelHelloworldObjC_classes"],
)