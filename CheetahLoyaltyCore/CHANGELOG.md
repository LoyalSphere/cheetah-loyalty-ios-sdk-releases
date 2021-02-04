# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [Core-1.9.1] - 2021-02-04

### Fixed
- Reenter Challenge completion associated type and model key path [#588]

[#588]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/588
[Core-1.9.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/84?closed=1

## [Core-1.9.0] - 2021-01-26

### Added
- Reenter challenge with attachments API [#577]
- Get challenge with location API [#580], [#581]

### Changed
- Requests dependencies with CheetahLoyaltyUtils [#579]
- Request adapter to create full path of the request [#579]
- Rename date extensions that has specific Cheetah formatting [#579]

### Removed
- Utility code from Core (transferred to CheetahLoyaltyUtils) [#579]:
	- `AnyCodable`, `AnyDecodable`, and `AnyEncodable`
	- URL and URLRequest Convertible 
	- URL Parameter Encoding
	- `Result` extensions

[#577]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/577
[#579]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/579
[#580]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/580
[#581]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/581
[Core-1.9.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/77?closed=1

## [Core-1.8.1] - 2021-01-12

### Fixed
- Access level of clip/unclip offer response api to public [#566]

[#566]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/566
[Core-1.8.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/73?closed=1

## [Core-1.8.0] - 2020-11-05

### Added
- `Configuration` public initializer [#537]
- Clip and unclip offer response OfferAPI static methods [#540]
- Server birthdate format constant [#543]
- Date and timestamp conversions for the server API responses [#547], [#548]
- Additional info dictionary to `APIError` [#557]

### Changed
- `Configuration.shared` to a variable [#537]
- Changed dependency version requirements to CheetahLoyaltyUtils 1.1.0 [#547], [#548]
- Built using Xcode 12 to support the iOS 14 SDK and Swift 5.3 [#556]

### Removed
- Unnecessary loading of bundle in initial value of `Configuration.shared` [#544]

[#537]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/537
[#540]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/540
[#543]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/543
[#544]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/544
[#547]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/547
[#548]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/548
[#556]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/556
[#557]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/557
[Core-1.8.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/68?closed=1

## [Core-1.7.0] - 2020-09-04
### Added
- Inline documentation for registeredDeviceToken defaults key [#507]
- `hasLaunchedOnce` Defaults Key [#507]
- `deleteCredentialsIfNeeded` method that deletes the credentials in the keychain when the app has not yet launched at least once. [#507]

[#507]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/507
[Core-1.7.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/56?closed=1

## [Core-1.6.0] - 2020-08-19
### Changed
- `APIError` access level to public [#490]

[#490]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/490
[Core-1.6.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/49?closed=1

## [Core-1.5.0] - 2020-08-10
### Added
- `Offer.OfferType` cases: [#460]
	- `coupon`
	- `noAction`
- Get Offers with responses API [#459]
- Dependency to `CheetahLoyaltyUtils` [#470]

### Changed
- `Reward`'s `expirationInterval` property type to `Int?` [#461]
- Utility code transferred to `CheetahLoyaltyUtils` [#470]

[#459]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/459
[#460]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/460
[#461]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/461
[#470]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/470
[Core-1.5.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/37?closed=1

## [Core-1.4.0] - 2020-07-14
### Changed
- Enable require only App Extension Safe API to YES [#446]
- `ProfileAttribute` to conform to `MutableProfileAttribute` [#445]
- Type properties of some models from optional to non-optional [#444]:
	- `GiftCard`'s `type` property
	- `FeedbackItem`'s `type` property
	- `MemeChallengeResponseSetting`'s `subtype` property
	- `Message`'s `type` property
	- `Offer`'s `type` property
	- `Reward`'s `type` property
- `Award`'s `status` property from String to an enum `Award.Status` [#435]

### Removed
- `canBeOpened()` instance extension method of `URL` as part of making `CheetahLoyaltyCore` App Extension Safe [#431]

[#431]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/431
[#435]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/435
[#444]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/444
[#445]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/445
[#446]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/446
[Core-1.4.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/32?closed=1

## [Core-1.3.0] - 2020-06-09
### Added
- Added `Certificate` and `Coupon` properties in `Offer.Response` and `Offer.ResponseInfo` [#371]
- Added `maximumMetric` and `minimumMetric` `String` properties in `Reward` [#375]
- Added `Reward.ResponseInfo` memberwise initializer [#393]
- Added `extraJSON` property in `Reward` [#391]

### Changed
- Changed `metricAmount` property type of `Reward.AttributeCombination` to `String` [#377]
- Changed `type` property type of `Reward` to `Reward.RewardType` enum [#378]
- Changed `redeemOptions` property name of `Reward` to `redemptionOptions` and type to an array of `RedemptionOptions` [#386]
- Changed `redemptionStatus` property type of `Reward` to `Reward.RedemptionStatus` [#401]

### Fixed
- Fixed client id header key in requests when access token is retrieved externally [#406]

[#371]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/371
[#375]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/375
[#377]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/377
[#378]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/378
[#386]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/386
[#391]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/391
[#393]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/393
[#401]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/401
[#406]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/406
[Core-1.3.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/27?closed=1

## [Core-1.2.1] - 2020-04-27
### Added
- Added validation of url [#343]
- Added `Reward.Response.ShippingAddress` model [#346]
- Added configuration for access tokens retrieved from an external source [#357]

### Changed
- Conform `Challenge.ResponseInfo` to `Equatable` [#349]
- Packaged framework into XCFramework with module stability [#358]

[#358]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/358
[#357]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/357
[#349]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/349
[#346]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/346
[#343]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/343
[Core-1.2.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/21?closed=1

## [Core-1.2.0] - 2020-03-11
### Added
- Add additional tests for Keychain error [#278]
- Add `extraJSON` property in `Offer` [#283]
- Add documentation for redeeming a reward [#284]
- Add `QuestionType` enumeration in `SurveyChallengeReponseSetting` [#287]
- Add `imageUrl` property in `ViewContentChallengeResponseSetting` [#307]
- Add `type` property in `UpdateProfileChallengResponseSetting.Attribute` [#325]
- Add `MutableProfileAttribute` protocol [#325][#337]

### Fixed
- Change `VideoChallengeResponseSetting`'s `videoSizeLimit` property type to `String` [#275]
- Adapt client info into log out request instead of access token in header [#339]

### Changed
- Moved initialization methods with literals in `_AnyEncodable` to `AnyCodable` and `AnyEncodable` [#277]
- Enqueue `.APIAccessTokenDidBecomeInvalid` notification in main queue [#280], [#339]
- Change `NewsfeedAPI.addNewPost`'s `feedName` parameter type to `String?` [#281]
- Change `SurveyChallengeReponseSetting`'s `questionType` property type to `SurveyChallengeReponseSetting.QuestionType` [#287]
- Change `MultiQuestionChallengeResponseSetting`'s `definitions` property type to `[Survey]` [#292]
- Remove unnecessary properties from `SurveyChallengeResponseSetting` [#299], [#303]
- Change `ViewContentChallengeResponseSetting`'s `subtype` property type to `ViewContentChallengeResponseSetting.Subtype` [#307], [#310]
- Consolidated custom `Notification` objects [#315]
- Change `ReferralChallengeResponseSetting`'s `shareableText` to a computed property [#318]
- Change `UpdateProfileChallengResponseSetting.Attribute`'s `defaultValue` property type to `AnyCodable?` [#325]
- Change `PhotoCaptionChallengeResponseSetting` to `MemeChallengeResponseSetting` [#330]
- Move completion callbacks and in shouldRetry to session delegate queue [#339]
- Refresh Token requests won't be retried [#340]
- Improve refreshing access token handling [#340]

[#275]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/275
[#277]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/277
[#278]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/278
[#280]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/280
[#281]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/281
[#283]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/283
[#284]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/284
[#287]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/287
[#292]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/292
[#299]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/299
[#303]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/303
[#307]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/307
[#310]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/310
[#315]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/315
[#318]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/318
[#325]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/325
[#330]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/330
[#337]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/337
[#339]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/339
[#340]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/340
[Core-1.2.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/17?closed=1

## [Core-1.1.4] - 2019-12-20
### Added
- Added `ProfileAttribute.Category` model [#269]

### Fixed
- Fixed unlike post http method [#273]
- Fixed properties of Preference not declared as public: [#271]
	- `isToggle`
	- `hasNoOption`
	- `hasYesOption`
	- `hasSelectedYes`

[#273]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/273
[#271]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/271
[#269]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/269
[Core-1.1.4]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/16?closed=1

## [Core-1.1.3] - 2019-12-18
### Added
- Added tests for `Place` conforming to `Equatable` [#267]

### Changed
- Change `Message.Attachment`'s `type` property type to `Message.Attachment.AttachmenType?` [#257], [#263]
- Removed `AuthenticationAPI.logOut`'s `accessToken` parameter to just use current access token saved in `API` [#256]
- Renamed *"Business-Unit"* header key to *"SL-Business-Unit"* [#262]
- Changed access control of `accessUsingUserPrescence` property of `KeychainItem` to public [#261]
- Renamed `accessUsingUserPrescence` to `accessControlWithUserPrescence` [#265]

### Fixed
- Fixed `Offer`'s `subheading` property not being decoded [#258], [#266]

[#267]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/267
[#266]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/266
[#265]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/265
[#263]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/263
[#262]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/262
[#261]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/261
[#258]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/258
[#257]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/257
[#256]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/256
[Core-1.1.3]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/15?closed=1

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
[Core-1.1.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/13?closed=1

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
[Core-1.1.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/10?closed=1

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
[Core-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/8?closed=1

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
[Core-1.0.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/6?closed=1

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
[Core-1.0.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/5?closed=1

## [Core-1.0.0] - 2019-09-06
### Added
- Models and API requests.
- Authentication Handling

[Core-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/1?closed=1
