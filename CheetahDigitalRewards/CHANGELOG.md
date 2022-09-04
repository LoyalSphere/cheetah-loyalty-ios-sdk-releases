# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Rewards-2.2.0] - 2022-09-04
### Changed
- Changed dependency version requirements to CheetahDigitalCore 2.3.0.

## [Rewards-2.1.1] - 2022-05-06
### Changed
- Changed dependency version requirements to CheetahDigitalCore 2.2.1

## [Rewards-2.1.0] - 2022-04-19
### Changed
- Built using Xcode 13.3.

## [Rewards-2.0.0] - 2022-01-21
### Changed
- Rename project and package name to `CheetahDigitalRewards`

[Rewards-2.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/99?closed=1

## [Rewards-1.3.3] - 2021-10-21Z
### Changed
- Move `Reward` and `Reward.Response` conformance to `DetailPresentable` into Tests [#615]

[#615]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/615
[Rewards-1.3.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/98?closed=1

## [Rewards-1.3.2] - 2021-10-15Z
### Changed
- Swiftlint configuration to support update and M1 Macs [#613]
- Changed dependency version requirements to CheetahLoyaltyCore 1.10.0, CheetahLoyaltyUI 1.10.0, and CheetahLoyaltyUtils 1.3.0 [#613]

### Fixed
- Incorrect Unit Tests [#614]

[#613]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/613
[#614]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/614
[Rewards-1.3.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/97?closed=1

## [Rewards-1.3.1] - 2021-01-29

### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.9.0, CheetahLoyaltyUI 1.9.1, and CheetahLoyaltyUtils 1.2.0 [#587]

[#587]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/587
[Rewards-1.3.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/83?closed=1

## [Rewards-1.3.0] - 2021-01-15

### Added
- Dark mode support using `CheetahAppBackgroundView` [#573]

### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.8.1 and CheetahLoyaltyUI 1.9.0 [#573]

[#573]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/573
[Rewards-1.3.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/75?closed=1

## [Rewards-1.2.3] - 2020-11-06
### Changed
- Rearrange sequence of setting up Reward and Redemption detail [#520]
- Update scroll views to use content layout guide [#538]
- Changed dependency version requirements to CheetahLoyaltyCore 1.8.0, CheetahLoyaltyUI 1.8.0, and CheetahLoyaltyUtils 1.1.0 [#552], [#553]
- Built using Xcode 12 to support the iOS 14 SDK and Swift 5.3 [#563]

[#520]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/520
[#538]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/538
[#552]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/552
[#553]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/553
[#563]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/563
[Rewards-1.2.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/61?closed=1

## [Rewards-1.2.2] - 2020-09-05
### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.7.0 and CheetahLoyaltyUI 1.7.0 [#516]
- Apply Changes to `DetailController` in Reward Detail [#516]

[#516]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/516
[Rewards-1.2.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/59?closed=1

## [Rewards-1.2.1] - 2020-08-19
### Added
- Add accessibility labels for views that are not default accessibility elements [#482]

### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.6.0 and CheetahLoyaltyUI 1.6.0 [#498]

### Fixed
- Function call of dictionary extension method, `filterVoid()` [#480]

[#480]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/480
[#482]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/482
[#498]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/498
[Rewards-1.2.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/46?closed=1

## [Rewards-1.2.0] - 2020-08-11
### Added
- Dependency to CheetahLoyaltyUtils 1.0.0 [#479]
### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.5.0 and CheetahLoyaltyUI 1.5.0 [#479]

[#479]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/479
[Rewards-1.2.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/45?closed=1

## [Rewards-1.1.0] - 2020-07-21
### Changed
- Change `awardStatus` type to `Award.Status` type [#448]
- Changed dependency version requirements to CheetahLoyaltyCore 1.4.0 and CheetahLoyaltyUI 1.4.0 [#452]

[#448]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/448
[#452]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/452
[Rewards-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/36?closed=1

## [Rewards-1.0.0] - 2020-06-17

### Added
- Reward and Redemption Detail View Controllers
- Reward Responders:
	- Certificate
	- Challenge
	- Generic
	- Physical
	- Metric Transfer

[Rewards-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/25?closed=1
