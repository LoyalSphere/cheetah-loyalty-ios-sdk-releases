# Cheetah Digital Rewards iOS

The Cheetah Digital Challenges iOS SDK contains a collection of components used to respond to *Rewards* of the Cheetah Digital platform.

## Requirements
* Deployment Target: iOS 11.0
* Xcode 11.x
* Swift 5.1
* `CheetahDigitalCore` v1.10.0
* `CheetahDigitalUI` v1.10.0
* `CheetahDigitalUtils` v1.3.0

## Installation

### Cocoapods

1. Open a terminal window then add the private podspec repo to the Cocoapods installation by entering the following:

```sh
pod repo add CheetahDigitalSDK https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git
```

2. Add a source for the CheetahDigitalSDK and add the `CheetahDigitalRewards` pod in your podfile:

```ruby
platform :ios, '11.0'

source 'https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git'
source 'https://github.com/CocoaPods/Specs.git'

target '<YourApp>' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

  pod 'CheetahDigitalRewards'
end
```

3. Open a terminal window to where your project and podfile is located and run the following to install the pod:

```sh
pod install
```


### Manually

1. Install [`CheetahDigitalUtils`](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/blob/master/CheetahDigitalUtils/README.md), [`CheetahDigitalCore`](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/blob/master/CheetahDigitalCore/README.md) and [`CheetahDigitalUI`](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/blob/master/CheetahDigitalUI/README.md) frameworks.
2. [Download the CheetahDigitalRewards SDK from the releases](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/releases).
2. Extract it then drag & drop CheetahDigitalRewards.xcframework to your project's directory.
3. In "Frameworks, Libraries, and Embedded Content" section under the "General" tab, click on the "+" button then "Add Other", and then "Add Files...".
4. Select the CheetahDigitalRewards.xcframework file and make sure that it is set to "Embed & Sign" in the "Embed" column in the "Frameworks, Libraries, and Embedded Content" section under the "General" tab.


## More
You can also check out our API Reference for more detailed information about our SDK.
