# Cheetah Loyalty Olo UI iOS

- [Requirements](#requirements)
- [Installation](#installation)
	* [Cocoapods](#cocoapods)
	* [Manually](#manually)
- [Usage](#usage)

## Requirements
* Deployment Target: iOS 11.0
* Xcode 11.x
* Swift 5.1
* `CheetahLoyaltyUI` v1.5.0
* `CheetahLoyaltyOloCore` v1.1.0
* `CheetahUtils` v1.0.0

## Installation

### Cocoapods

1. Open a terminal window then add the private podspec repo to the Cocoapods installation by entering the following:

```sh
pod repo add CheetahLoyaltyOloUI https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git
```

2. Add a source for the CheetahLoyaltySDK and add the `CheetahLoyaltyOloUI` pod in your podfile:

```ruby
platform :ios, '11.0'

source 'https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git'
source 'https://github.com/CocoaPods/Specs.git'

target '<YourApp>' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

  pod 'CheetahLoyaltyOloUI'
end
```

3. Open a terminal window to where your project and podfile is located and run the following to install the pod:

```sh
pod install
```

### Manually

1. [Download the CheetahLoyaltyOloUI SDK from the releases](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/releases).
2. Extract it then drag & drop CheetahLoyaltyOloUI.xcframework to your project's directory.
3. In "Frameworks, Libraries, and Embedded Content" section under the "General" tab, click on the "+" button then "Add Other", and then "Add Files...".
4. Select the CheetahLoyaltyOloUI.xcframework file and make sure that it is set to "Embed & Sign" in the "Embed" column in the "Frameworks, Libraries, and Embedded Content" section under the "General" tab.

## Usage

### Configuration
Before using the Olo iOS framework, a configuration file is needed to determine the settings it needs upon sending requests. The configuration file is a plist named **OLOSDK-Info**. The file needs to be included in the project bundle and should include the following details:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>CLIENT_URL</key>
	<string><your_client_url></string>
	<key>API_VERSION</key>
	<string><api_version></string>
	<key>API_KEY</key>
	<string><your_api_key></string>
	<key>PROVIDER_SLUG</key>
	<string><your_provider_slug></string>
</dict>
</plist>
```

The values included in the plist are provided by Olo.

### Ordering

#### To show the Complete Ordering Process
The code below returns a View Controller that shows the 5 stages of Olo Ordering

```
OrderProgressView.oloProgressViewControllerFactory()
```
