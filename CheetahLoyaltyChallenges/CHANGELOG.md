# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Challenges-1.3.3] - 2021-10-15Z
### Changed
- Swiftlint configuration to support update and M1 Macs [#609]
- Dependency version requirements to CheetahLoyaltyCore 1.10.0, CheetahLoyaltyUI 1.10.0, and CheetahLoyaltyUtils 1.3.0 [#609]

### Fixed
- Incorrect Unit Tests [#610]

[#609]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/609
[#610]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/610
[Challenges-1.3.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/94?closed=1

## [Challenges-1.3.2] - 2021-02-08

### Fixed
- Sending of notification of challenge updated upon responding to a challenge [#593]

[#593]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/593
[Challenges-1.3.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/88?closed=1

## [Challenges-1.3.1] - 2021-02-05

### Added
- Missing response id to survey responder for challenge static method [#591]

### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.9.2 [#592]

[#591]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/591
[#592]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/592
[Challenges-1.3.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/87?closed=1

## [Challenges-1.3.0] - 2021-02-04

### Added
- Reenter Challenge Responder [#589]

### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.9.1 [#589]

[#589]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/589
[Challenges-1.3.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/85?closed=1

## [Challenges-1.2.1] - 2021-01-28

### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.9.0, CheetahLoyaltyUI 1.9.1, and CheetahLoyaltyUtils 1.2.0 [#582]

[#582]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/582
[Challenges-1.2.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/78?closed=1

## [Challenges-1.2.0] - 2021-01-15

### Added
- Dark mode support using `CheetahAppBackgroundView` [#572]

### Changed
- Text fields in meme type challenge to floating text fields on text fields [#576]
- Dependency version requirements to CheetahLoyaltyCore 1.8.1, CheetahLoyaltyUI 1.9.0 [#572]

### Fixed
- Meme color picker background color [#575]

[#572]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/572
[#575]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/575
[#576]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/576
[Challenges-1.2.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/74?closed=1

## [Challenges-1.1.3] - 2020-11-06

### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.8.0, CheetahLoyaltyUI 1.8.0, and CheetahLoyaltyUtils 1.1.0 [#549]
- Use content layout guide in for scroll views [#534]
- Built using Xcode 12 to support the iOS 14 SDK and Swift 5.3

[#534]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/534
[#549]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/549
[Challenges-1.1.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/66?closed=1

## [Challenges-1.1.2] - 2020-09-04
### Added
- Accessibility labels [#502]

### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.7.0 and CheetahLoyaltyUI 1.7.0 [#515]

[#502]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/502
[#515]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/515
[Challenges-1.1.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/53?closed=1

## [Challenges-1.1.1] - 2020-08-19
### Changed
- Pass placeholder parameter for image loader methods [#497]
- Changed dependency version requirements to CheetahLoyaltyCore 1.6.0 and CheetahLoyaltyUI 1.6.0 [#497]

[#497]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/477
[Challenges-1.1.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/52?closed=1

## [Challenges-1.1.0] - 2020-08-11
### Added
- Dependency to CheetahLoyaltyUtils 1.0.0 [#477]

### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.5.0 and CheetahLoyaltyUI 1.5.0 [#477]

[#477]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/477
[Challenges-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/44?closed=1

## [Challenges-1.0.3] - 2020-07-21
### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.4.0 and CheetahLoyaltyUI 1.4.0 [#451]

### Fixed
- Fixed state not set to content after loading [#437]

[#437]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/437
[#451]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/451
[Challenges-1.0.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/35?closed=1

## [Challenges-1.0.2] - 2020-06-17

### Changed
- Set button height constraint to 44 [#384]
- Changed dependency version requirements to CheetahLoyaltyCore 1.3.0 and CheetahLoyaltyUI 1.3.0 [#427]

[#384]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/384
[#427]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/427
[Challenges-1.0.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/30?closed=1

## [Challenges-1.0.1] - 2020-05-11

### Added
- Add title to navigation bar of challenge responders [#360]
- Set font styles for labels [#367]

### Changed
- Module Stability and XCFrameworks support [#369]

### Fixed
- Handle unsupported post messages to prevent the HTML game from crashing [#356]

[#356]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/356
[#360]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/360
[#367]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/367
[#369]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/369
[Challenges-1.0.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/23?closed=1

## [Challenges-1.0.0] - 2020-03-13

### Added
- Added *Challenge* responders for:
	- Update avatar challenge
	- Check-in challenge
	- Game challenge
	- Generic challenge
	- Upload media challenge
		- Upload photo
		- Upload video
	- Meme challenge
	- Multi question challenge
	- Update preferences challenge
	- Update profile challenge
	- Referral challenge
	- Survey challenge
		- Multiple Choice
		- Numeric
		- Rating
		- Text
	- View Content challenge
		- View Photo
		- View URL
- Added `ChallengeResponseDetailViewController`
- Added `ShareChallengeToSocialMediaDelegate` protocol

[Challenges-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/19?closed=1
