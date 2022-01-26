# Cheetah Digital Notifications iOS

The Cheetah Digital Notifications iOS SDK contains a collection of classes, methods, and protocols that encapsulates implementation of notification related features.

## Requirements
* Deployment Target: iOS 11.0
* Xcode 11.x
* Swift 5.1
* `CheetahDigitalCore` v1.10.0
* `CheetahDigitalUtils` v1.3.0

## Installation

### Cocoapods

1. Open a terminal window then add the private podspec repo to the Cocoapods installation by entering the following:

```sh
pod repo add CheetahDigitalSDK https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git
```

2. Add a source for the CheetahDigitalSDK and add the `CheetahDigitalNotifications` pod in your podfile:

```ruby
platform :ios, '11.0'

source 'https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git'
source 'https://github.com/CocoaPods/Specs.git'

target '<YourApp>' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

  pod 'CheetahDigitalNotifications'
end
```

3. Open a terminal window to where your project and podfile is located and run the following to install the pod:

```sh
pod install
```


### Manually

1. Install [`CheetahDigitalUtils`](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/blob/master/CheetahDigitalUtils/README.md) and [`CheetahDigitalCore `](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/blob/master/CheetahDigitalCore/README.md) framework.
2. [Download the CheetahDigitalNotifications SDK from the releases](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/releases).
3. Extract it then drag & drop CheetahDigitalNotifications.framework to your project's directory.
4. In "Frameworks, Libraries, and Embedded Content" section under the "General" tab, click on the "+" button then "Add Other", and then "Add Files...".
5. Select the CheetahDigitalNotifications.framework file and make sure that it is set to "Embed & Sign" in the "Embed" column in the "Frameworks, Libraries, and Embedded Content" section under the "General" tab.

## More
You can also check out our API Reference for more detailed information about our SDK.
