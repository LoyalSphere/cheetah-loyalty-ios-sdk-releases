# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Core-1.1.2] - 2019-12-23
### Added
- Added `businessUnit` property in `Configuration` [#235]
- Added `Configuration.businessUnit`'s value if existing and not empty, in session HTTP headers [#235]
- Added `getRefreshToken` to API [#239]
- Added `ListInfo` property in `NearbyPlaces` [#242]

### Changed
- When a request results in an expired token error and there is no refresh token present in `API.getRefreshToken`, the request won't be retried and just return the associated error [#239]
- Changed `API.setCredentials` parameter `refreshToken`'s type to `String?` with `nil` as a default value [#239]
- Replaced `ListInfo` conformation to `Decodable` into `Codable` and add conformation to `Equatable` [#242]
- Added default value to the `action` parameter of `MessagesAPI.trackMessage` [#246]
- In `KeychainError.localizedDescription`, return the `OSStatus` in a string if the iOS version is less than 11.3 and return `SecCopyErrorMessageString` of the `OSStatus` otherwise [#247]
- Replaced `AuthenticationAPI.logOut` calls to post `APIAccessTokenDidBecomeInvalid` notification instead [#248]
- Changed `AuthenticationAPI.logOut` implementation to send a logout request [#248]
- Renamed `AuthenticationAPI.login` to `AuthenticationAPI.logIn` to better indicate intent [#248]
- Updated `CheetahLoyaltyCore/README.md` usage documentation with the following [#249]:
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

[#235]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/235
[#239]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/239
[#242]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/242
[#246]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/246
[#247]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/247
[#248]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/248
[#249]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/249

## [Core-1.1.1] - 2019-11-21
### Added
- Added `UpdateProfileChallengeResponseSetting.SubType` enum [#217]
- Added `UpdateProfileChallengeAttribute` protocol [#217]
- Added `apple` case for `AuthenticationAPI.SocialLoginType` [#220]
- Added `hasYesOption`, `hasNoOption`, `hasSelectedYes`, `isToggle` properties to `Preference` [#218]
- Added helper methods for `Preference` domains [#218]
- Added fetching list and detail usage documentation in `README` [#219]
- Added removing user domains in `Preference` [#222]
- Added `Reward.ResponseInfo` [#224]
- Added `imageUrl` and `thumbImageUrl` properties in `Reward.Category` [#224]

### Changed
- Changed `UpdateProfileChallengeResponseSetting.Attribute`'s `value` property type to `AnyCodable` [#217]
- Made `Preference` conform to `UpdateProfileChallengeAttribute` [#214]
- Changed `UpdateProfileChallengeResponseSetting`'s `attributes` property type to `UpdateProfileChallengeAttribute` [#217]
- On decoding of an `UpdateProfileChallengeResponseSetting`, this property may contain an array of `UpdateProfileChallengeResponseSetting.Attribute` or an array of `Preference` as both of these now conform to `UpdateProfileChallengeAttribute` [#217]
- Added `isMultiSelect` boolean associated value to the `selectDomains` case in `PreferencesRequest` [#218]
- Changed `Reward` `embedded` property type to `AnyCodable` [#224]
- Changed redeeeming of reward API completion closure associated value type to `Reward.ResponseInfo` [#224]
- Changed `UpdateProfileChallengeResponseSetting` `value` property type to `AnyCodable?` [#225]
- Changed `getPunchCard` `id` parameter type to `Int` [#226]
- Renamed `Offer.RespondInfo` to `Offer.ResponseInfo` [#227]

### Fixed
- Fixed login with social network grant type by changing it from `password` to `assertion` [#216]
- Fixed serializing Update Profile Challenges with member preference subtype. [#217]
- Added missing `Equatable` conformance to [#223]:
	- `Challenge.MetricPrize`
	- `CountriesStates`
	- `CountriesStates.Country`
	- `Offer.ResponseInfo`
	- `NearbyPlaces`
	- `Product.Category`
	- `Reward.Response`
	- `Reward.Category`

### Removed
- Removed `punch` API call [#221]
- Removed `Reward.Embedded` [#224]
- Removed `Reward.GiftCard` [#224]

[#216]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/216
[#217]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/217
[#218]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/218
[#219]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/219
[#220]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/220
[#221]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/221
[#222]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/222
[#223]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/223
[#224]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/224
[#225]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/225
[#226]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/226
[#227]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/227

## [Core-1.1.0] - 2019-11-08
### Added
- Added `HTTPHeaders` typealias [#214]
- Made `MultipartAttachment` conform to `Equatable` [#214]
- Added ability to add addtional HTTP Headers, parameters or attachments on converting a `URLRequestConvertible` to a `URLRequest` with `asURLRequest`  [#214]

### Changed
- Built using Xcode 11 to support the iOS 13 SDK and Swift 5.1
- `KeychainItem` can now write with a security access control object. [#211]
- `KeychainItem` can now write Data and JSON dictionaries. [#211]
- API calls will now have the client id and secret in its parameters when there is no access token saved [#214]

### Fixed
- Fixed client id and secret not being added in `parameters` of the `signUp(parameters: Parameters?)` case of `AuthenticationRequest` [#210]

[#210]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/210
[#211]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/211
[#214]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/214

## [Core-1.0.2] - 2019-10-11
### Added
- Added `USER_AGENT_NAME` Configuration property. [#196]
- Added `DeviceAPI` requests for registering devices for push notifications. [#202]
- Added `InfoAPI` requests to get additional application information. [#200]
- Added more info on the documentation of setting up the configuration file and the precondition failure message. [#205]

### Fixed
- Corrected the user agent header string using the `USER_AGENT_NAME` Configuration property. [#196]
- Fixed `Reward` property `responseCurrencyAmount` type by changing it from `Double` to `String`. [#199]

### Changed
- Changed `KeychainItem` struct access control to public. [#197]

[#196]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/196
[#197]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/197
[#199]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/199
[#200]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/200
[#202]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/202
[#205]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/205

## [Core-1.0.1] - 2019-09-25
### Added
- Added CHANGELOG file.
- Added `isGeofencingEnabled` in Configuration. [#180]
- Added `NearbyPlaces` model and API requests. [#178]

### Fixed
- Added public memberwise initalizers of structs. [#184]
- Added missing strip-frameworks.sh. [#179]
- Changed access control of Configuration. [#181]

[#178]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/178
[#179]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/179
[#180]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/180
[#181]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/181
[#184]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/184

## [Core-1.0.0] - 2019-09-06
### Added
- Models and API requests.
- Authentication Handling

[Core-1.1.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/10?closed=1
[Core-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/8?closed=1
[Core-1.0.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/6?closed=1
[Core-1.0.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/5?closed=1
[Core-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/1?closed=1
