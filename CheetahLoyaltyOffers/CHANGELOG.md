# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

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
