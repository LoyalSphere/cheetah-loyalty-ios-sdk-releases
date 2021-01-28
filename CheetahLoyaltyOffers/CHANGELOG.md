# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Offers-1.4.1] - 2021-01-28

### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.9.0, CheetahLoyaltyUI 1.9.1, and CheetahLoyaltyUtils 1.2.0 [#585]

[#585]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/585
[Offers-1.4.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/81?closed=1

## [Offers-1.4.0] - 2021-01-15

### Added
- Clip multiple offers at one time [#565]
- Offer response detail clipping [#571]
- Dark mode support using `CheetahAppBackgroundView` [#574]

### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.8.1, and CheetahLoyaltyUI 1.9.0 [#574]

[#565]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/565
[#571]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/571
[#574]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/574
[Offers-1.4.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/72?closed=1

## [Offers-1.3.1] - 2020-11-06
### Changed
- Dependency version requirements to CheetahLoyaltyCore 1.8.0, CheetahLoyaltyUI 1.8.0, and CheetahLoyaltyUtils 1.1.0 [#554]
- Built using Xcode 12 to support the iOS 14 SDK and Swift 5.3 [#561]

### Fixed
- `OfferCouponListController` and `OfferCouponClippedListController` init method visibility [#532]

[#532]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/532
[#554]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/554
[#561]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/561
[Offers-1.3.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/65?closed=1

## [Offers-1.3.0] - 2020-09-10
### Added
- Load parameters property for Offer Carousel [#522]
- Update with result generic method in Offer Detail [#526]

### Changed
- Replace setupContent with overridden setupDetails in Offer Detail [#526]
- Changed dependency version requirements to CheetahLoyaltyUI 1.7.2 [#526]

### Fixed
- Remove setting of page indicator tint to white in auto scroll of Offer Carousel [#521]

[#521]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/521
[#522]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/522
[#526]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/526
[Offers-1.3.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/62?closed=1

## [Offers-1.2.0] - 2020-09-07
### Added
- Accessibility labels [#503]
- `setupContent` method consolidating setup of the content of Offer Detail Controller [#506]
- Check before auto scrolling and enqueue in main queue of Offer Carousel [#517]

### Changed
- Offer Detail Layout to use Scroll View Content Layout [#512]
- Removed some height restrictions on Labels in Offer Detail Layout [#512]
- Changed dependency version requirements to CheetahLoyaltyCore 1.7.0 and CheetahLoyaltyUI 1.7.1 [#519]

[#506]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/506
[#512]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/512
[#517]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/517
[#519]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/519
[Offers-1.2.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/54?closed=1

## [Offers-1.1.0] - 2020-08-19
### Added
- View controller parameter in share method of offer detail delegate [#483], [#499]
- Setup barcode in offer detail delegate [#484], [#499]

### Changed
- Load parameters property and refactor load content for consistency in offer lists [#487], [#501]
- Changed dependency version requirements to CheetahLoyaltyCore 1.6.0 and CheetahLoyaltyUI 1.6.0 [#500]

### Removed
- includeClippedStatus parameter in response detail factory method [#485]

[#483]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/483
[#484]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/484
[#485]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/485
[#487]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/487
[#499]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/499
[#500]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/500
[#501]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/501
[Offers-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/48?closed=1

## [Offers-1.0.0] - 2020-08-12

### Added
- Offer carousel controller
- Offer detail controller and view controller
- Offer response detail controller
- Offer list controller
- Offer coupon list controller
- Offer coupon clipped list controller
- Offer coupon segmented controller

[Offers-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/40?closed=1
