# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Core-1.2.0 - 2020-03-09
### Added
- Add additional tests for Keychain error
- Add `extraJSON` property in `Offer`
- Add documentation for redeeming a reward
- Add `QuestionType` enumeration in `SurveyChallengeReponseSetting`
- Add `imageUrl` property in `ViewContentChallengeResponseSetting`
- Add `type` property in `UpdateProfileChallengResponseSetting.Attribute`
- Add `MutableProfileAttribute` protocol

### Fixed
- Change `VideoChallengeResponseSetting`'s `videoSizeLimit` property type to `String`
- Adapt client info into log out request instead of access token in header

### Changed
- Moved initialization methods with literals in `_AnyEncodable` to `AnyCodable` and `AnyEncodable`
- Enqueue `.APIAccessTokenDidBecomeInvalid` notification in main queue
- Change `NewsfeedAPI.addNewPost`'s `feedName` parameter type to `String?`
- Change `SurveyChallengeReponseSetting`'s `questionType` property type to `SurveyChallengeReponseSetting.QuestionType`
- Change `MultiQuestionChallengeResponseSetting`'s `definitions` property type to `[Survey]`
- Configure CheetahLoyaltyCore to build XCFrameworks
- Remove unnecessary properties from `SurveyChallengeResponseSetting`
- Change `ViewContentChallengeResponseSetting`'s `subtype` property type to `ViewContentChallengeResponseSetting.Subtype`
- Consolidated custom `Notification` objects
- Change `ReferralChallengeResponseSetting`'s `shareableText` to a computed property
- Change `UpdateProfileChallengResponseSetting.Attribute`'s `defaultValue` property type to `AnyCodable?`
- Change `PhotoCaptionChallengeResponseSetting` to `MemeChallengeResponseSetting`
- Move completion callbacks and in shouldRetry to session delegate queue

## Core-1.1.4 - 2019-12-20
### Added
- Added `ProfileAttribute.Category` model

### Fixed
- Fixed unlike post http method
- Fixed properties of Preference not declared as public:
	- `isToggle`
	- `hasNoOption`
	- `hasYesOption`
	- `hasSelectedYes`

## Core-1.1.3 - 2019-12-18
### Added
- Added tests for `Place` conforming to `Equatable`

### Changed
- Change `Message.Attachment`'s `type` property type to `Message.Attachment.AttachmenType?`
- Removed `AuthenticationAPI.logOut`'s `accessToken` parameter to just use current access token saved in `API`
- Renamed *"Business-Unit"* header key to *"SL-Business-Unit"*
- Changed access control of `accessUsingUserPrescence` property of `KeychainItem` to public
- Renamed `accessUsingUserPrescence` to `accessControlWithUserPrescence`

### Fixed
- Fixed `Offer`'s `subheading` property not being decoded

## Core-1.1.2 - 2019-12-23
### Added
- Added `businessUnit` property in `Configuration`
- Added `Configuration.businessUnit`'s value if existing and not empty, in session HTTP headers
- Added `getRefreshToken` to API
- Added `ListInfo` property in `NearbyPlaces`

### Changed
- When a request results in an expired token error and there is no refresh token present in `API.getRefreshToken`, the request won't be retried and just return the associated error
- Changed `API.setCredentials` parameter `refreshToken`'s type to `String?` with `nil` as a default value
- Replaced `ListInfo` conformation to `Decodable` into `Codable` and add conformation to `Equatable`
- Added default value to the `action` parameter of `MessagesAPI.trackMessage`
- In `KeychainError.localizedDescription`, return the `OSStatus` in a string if the iOS version is less than 11.3 and return `SecCopyErrorMessageString` of the `OSStatus` otherwise
- Replaced `AuthenticationAPI.logOut` calls to post `APIAccessTokenDidBecomeInvalid` notification instead
- Changed `AuthenticationAPI.logOut` implementation to send a logout request
- Renamed `AuthenticationAPI.login` to `AuthenticationAPI.logIn` to better indicate intent
- Updated `CheetahLoyaltyCore/README.md` usage documentation with the following:
	- Content outline
	- Signing Up
	- Logging In with Social Networks
	- Refreshing Access Token Manually
	- Logging Out
	- Checking for version upgrades
	- Fetching List of Nearby Places
	- Registering device for Push Notifications
	- Tracking a Message from Push Notifications
	- Responding to a Challenge
	- Responding to an Offer
	- Clipping or Unclipping an Offer
	- Submitting Feedback

## Core-1.1.1 - 2019-11-21
### Added
- Added `UpdateProfileChallengeResponseSetting.SubType` enum
- Added `UpdateProfileChallengeAttribute` protocol
- Added `apple` case for `AuthenticationAPI.SocialLoginType`
- Added `hasYesOption`, `hasNoOption`, `hasSelectedYes`, `isToggle` properties to `Preference`
- Added helper methods for `Preference` domains
- Added fetching list and detail usage documentation in `README`
- Added removing user domains in `Preference`
- Added `Reward.ResponseInfo`
- Added `imageUrl` and `thumbImageUrl` properties in `Reward.Category`

### Changed
- Changed `UpdateProfileChallengeResponseSetting.Attribute`'s `value` property type to `AnyCodable`
- Made `Preference` conform to `UpdateProfileChallengeAttribute`
- Changed `UpdateProfileChallengeResponseSetting`'s `attributes` property type to `UpdateProfileChallengeAttribute`
- On decoding of an `UpdateProfileChallengeResponseSetting`, this property may contain an array of `UpdateProfileChallengeResponseSetting.Attribute` or an array of `Preference` as both of these now conform to `UpdateProfileChallengeAttribute`
- Added `isMultiSelect` boolean associated value to the `selectDomains` case in `PreferencesRequest`
- Changed `Reward` `embedded` property type to `AnyCodable`
- Changed redeeeming of reward API completion closure associated value type to `Reward.ResponseInfo`
- Changed `UpdateProfileChallengeResponseSetting` `value` property type to `AnyCodable?`
- Changed `getPunchCard` `id` parameter type to `Int`
- Renamed `Offer.RespondInfo` to `Offer.ResponseInfo`

### Fixed
- Fixed login with social network grant type by changing it from `password` to `assertion`
- Fixed serializing Update Profile Challenges with member preference subtype
- Added missing `Equatable` conformance to:
	- `Challenge.MetricPrize`
	- `CountriesStates`
	- `CountriesStates.Country`
	- `Offer.ResponseInfo`
	- `NearbyPlaces`
	- `Product.Category`
	- `Reward.Response`
	- `Reward.Category`

### Removed
- Removed `punch` API call
- Removed `Reward.Embedded`
- Removed `Reward.GiftCard`

## Core-1.1.0 - 2019-11-08
### Added
- Added `HTTPHeaders` typealias
- Made `MultipartAttachment` conform to `Equatable`
- Added ability to add addtional HTTP Headers, parameters or attachments on converting a `URLRequestConvertible` to a `URLRequest` with `asURLRequest`

### Changed
- Built using Xcode 11 to support the iOS 13 SDK and Swift 5.1
- `KeychainItem` can now write with a security access control object
- `KeychainItem` can now write Data and JSON dictionaries
- API calls will now have the client id and secret in its parameters when there is no access token saved

### Fixed
- Fixed client id and secret not being added in `parameters` of the `signUp(parameters: Parameters?)` case of `AuthenticationRequest`

## Core-1.0.2 - 2019-10-11
### Added
- Added `USER_AGENT_NAME` Configuration property.
- Added `DeviceAPI` requests for registering devices for push notifications
- Added `InfoAPI` requests to get additional application information
- Added more info on the documentation of setting up the configuration file and the precondition failure message.

### Fixed
- Corrected the user agent header string using the `USER_AGENT_NAME` Configuration property
- Fixed `Reward` property `responseCurrencyAmount` type by changing it from `Double` to `String`

### Changed
- Changed `KeychainItem` struct access control to public

## Core-1.0.1 - 2019-09-25
### Added
- Added CHANGELOG file.
- Added `isGeofencingEnabled` in Configuration
- Added `NearbyPlaces` model and API requests

### Fixed
- Added public memberwise initalizers of structs
- Added missing strip-frameworks.sh
- Changed access control of Configuration

## Core-1.0.0 - 2019-09-06
### Added
- Models and API requests
- Authentication Handling
