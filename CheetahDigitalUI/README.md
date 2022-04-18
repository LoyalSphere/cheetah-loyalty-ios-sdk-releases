# Cheetah Digital UI iOS

The Cheetah Digital UI iOS SDK is a collection of UI components used for creating Cheeth Digital iOS applications.

## Requirements
* Deployment Target: iOS 11.0
* Xcode 11.x
* Swift 5.1
* CheetahDigitalUtils 1.3.0

## Installation

### Cocoapods

1. Open a terminal window then add the private podspec repo to the Cocoapods installation by entering the following:

```sh
pod repo add CheetahDigitalSDK https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git
```

2. Add a source for the CheetahDigitalSDK and add the `CheetahDigitalUI` pod in your podfile:

```ruby
platform :ios, '11.0'

source 'https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git'
source 'https://github.com/CocoaPods/Specs.git'

target '<YourApp>' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

  pod 'CheetahDigitalUI'
end
```

3. Open a terminal window to where your project and podfile is located and run the following to install the pod:

```sh
pod install
```

### Manually

1. Install [`CheetahDigitalUtils`](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/blob/master/CheetahDigitalUtils/README.md) framework.
2. [Download the CheetahDigitalUI SDK from the releases](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/releases).
3. Extract it then drag & drop CheetahDigitalUI.xcframework to your project's directory.
4. In "Frameworks, Libraries, and Embedded Content" section under the "General" tab, click on the "+" button then "Add Other", and then "Add Files...".
5. Select the CheetahDigitalUI.xcframework file and make sure that it is set to "Embed & Sign" in the "Embed" column in the "Frameworks, Libraries, and Embedded Content" section under the "General" tab.

## More
You can also check out our API Reference for more detailed information about our SDK.
