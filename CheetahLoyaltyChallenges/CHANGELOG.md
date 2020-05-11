# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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
