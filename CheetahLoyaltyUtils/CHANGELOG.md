# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Utils-1.2.0] - 2021-01-26

### Added
- Utility components from Cheetah Loyalty Core [#578]:
	- URL Parameter Encoding
	- URL and URL Request Convertible
	- Result Extensions
	- Any Codable
- Parameter Encoding Types [#578]

### Changed
- `MultipartAttachements` to be accessible outside of `URLRequest` [#578]

[#578]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/578
[Utils-1.2.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/76?closed=1

## [Utils-1.1.0] - 2020-11-04
### Added
- `UIImage` extension methods for compressing and scaling images [#539]

### Changed
- Built using Xcode 12 to support the iOS 14 SDK and Swift 5.3 [#555]

### Removed
- Time stamp and date formatting related directly to Core [#545], [#546]

[#539]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/539
[#545]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/545
[#546]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/546
[#555]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/555
[Utils-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/67?closed=1

## [Utils-1.0.0] - 2020-08-10
### Added
- Extension methods for:
	- Array operations
	- Bundle and resource loading
	- Data hex convertion and JSON serialization
	- Date Formatting
	- Dictionary Void Filtering
	- Encodable JSON serialization
	- JSONDecoder decoding for specified key path
	- KeyedDecodingContainer decoding with default value
	- Notification initializer with Cheetah Notification
	- NotificaiontCenter add observer for Cheetah Notification
	- String operations, validation and formatting
	- UIDevice device name listing
- Keychain Item
- Localizer
- CheetahNotification

[Utils-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/39?closed=1
