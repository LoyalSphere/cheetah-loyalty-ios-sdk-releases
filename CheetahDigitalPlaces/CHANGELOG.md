# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Places-2.1.0] - 2022-04-18
### Changed
- Built using Xcode 13.3.

## [Places-2.0.0] - 2022-01-21
### Changed
- Rename project and package name to `CheetahDigitalPlaces`

### Removed
- Unneeded dependencies in tests

[Places-2.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/99?closed=1

## [Places-1.2.5] - 2021-10-15Z
### Changed
- Swiftlint configuration to support update and M1 Macs [#612]
- Dependency version requirements to CheetahLoyaltyCore 1.10.0 and CheetahLoyaltyUtils 1.3.0 [#612]

[#612]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/612
[Places-1.2.5]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/96?closed=1

## [Places-1.2.4] - 2021-01-28
### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.9.0 [#586]

[#586]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/562
[Places-1.2.4]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/82?closed=1

## [Places-1.2.3] - 2020-11-06
### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.8.0 [#550]
- Built using Xcode 12 to support the iOS 14 SDK and Swift 5.3 [#562]

[#550]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/550
[#562]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/562
[Places-1.2.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/69?closed=1

## [Places-1.2.2] - 2020-09-04
### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.7.0 [#513]

[#513]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/513
[Places-1.2.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/57?closed=1

## [Places-1.2.1] - 2020-08-19
### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.6.0 [#495]

[#495]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/495
[Places-1.2.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/50?closed=1

## [Places-1.2.0] - 2020-08-11
### Added
- Dependency to CheetahLoyaltyUtils 1.0.0 [#478]
### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.5.0 [#478]
- Use utilities `CheetahLoyaltyUtils` [#478]

[#478]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/478
[Places-1.2.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/43?closed=1

## [Places-1.1.5] - 2020-07-21
### Changed
- Changed dependency version requirements to CheetahLoyaltyCore 1.4.0 [#453]

[#453]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/453
[Places-1.1.5]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/38?closed=1

## [Places-1.1.4] - 2020-06-25
### Changed
- Removed dependency requirements for CheetahLoyaltyUI [#430]
- Localizable strings now retrieved from main bundle [#430]

### Fixed
- Removed lingering references to dependency on CheetahLoyaltyUI [#430]

[#430]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/430
[Places-1.1.4]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/31?closed=1

## [Places-1.1.3] - 2020-06-17
### Changed
- Handle scheduling of local notification natively [#380]
- Changed dependency version requirements to CheetahLoyaltyCore 1.3.0 and CheetahLoyaltyUI 1.3.0 [#426]

[#380]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/380
[#426]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/426
[Places-1.1.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/28?closed=1

## [Places-1.1.2] - 2020-05-11

### Changed
- Module Stability and XCFrameworks support [#368]
- Changed dependency version requirements to CheetahLoyaltyCore 1.2.1 and CheetahLoyaltyUI 1.2.1 [#368]

[#368]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/368
[Places-1.1.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/24?closed=1

## [Places-1.1.1] - 2020-03-12

### Changed
- Consolidated custom events [#316]
- Changed dependency version requirements to CheetahLoyaltyCore 1.2.0 and CheetahLoyaltyUI 1.2.0 [#341]

[#316]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/316
[#341]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/341
[Places-1.1.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/20?closed=1

## [Places-1.1.0] - 2019-12-10

### Added
- Setup Places host application for testing [#254]
- Added checking if location manager is currently requesting for authorization [#250]

### Changed
- Changed `LocationManager.Event` cases [#254]
- Changed handling of `CLLocationManagerDelegate` events [#254]
- Changed place's coordinates property to `CLLocationCoordinate2D` instead of tuple [#252]

[#250]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/250
[#252]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/252
[#254]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/254
[Places-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/14?closed=1

## [Places-1.0.0] - 2019-11-22
### Added
- Added `GeofenceClientEventsManager`
- Added `GeofenceManager`
- Added `LocationManager`
- Added extension of `Place` object to conform on `GeofencePlace`
- Added `GeofencePlace` protocol

[Places-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/3?closed=1
