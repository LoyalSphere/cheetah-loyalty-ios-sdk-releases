# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Places-1.1.1] - 2020-03-12

### Changed
- Consolidated custom events [#316]
- Changed dependency version requirements to CheetahLoyaltyCore 1.2.0 and CheetahLoyaltyUI 1.2.0 [#341]

[#316]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/316
[#341]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/341

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

## [Places-1.0.0] - 2019-11-22
### Added
- Added `GeofenceClientEventsManager`
- Added `GeofenceManager`
- Added `LocationManager`
- Added extension of `Place` object to conform on `GeofencePlace`
- Added `GeofencePlace` protocol

[Places-1.1.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/20?closed=1
[Places-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/14?closed=1
[Places-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/3?closed=1
