# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [UI-1.7.2] - 2020-09-10
### Changed
- Remove setting of titles of Floating text fields and text views to uppercased [#523], [#525]

### Fixed
- Remove calling of `setupDetails` on setting of `detailProvider` in `BaseDetailController` [#524]

[#525]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/525
[#524]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/524
[#523]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/523
[UI-1.7.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/63?closed=1

## [UI-1.7.1] - 2020-09-07
### Changed
- `BaseDetailController` as a subclass of `NSObject` [#518]

[#518]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/518
[UI-1.7.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/60?closed=1

## [UI-1.7.0] - 2020-09-04
### Added
- Accessibility for views without default accessibility [#504]
- `BaseDetailController` base class for `DetailController` [#508]

### Changed
- Move `setupDetails` from `DetailViewController` to `DetailController` [#508]
- Color sets and image assets naming convention [#510]

### Fixed
- Applying Text Appearance on elements with title text attributes [#509]

### Removed
- Text Appearance Text Color [#509]
- Highlighted and disabled button text appearances [#511]

[#511]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/511
[#510]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/510
[#509]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/509
[#508]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/508
[#504]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/504
[UI-1.7.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/55?closed=1

## [UI-1.6.0] - 2020-08-19
### Added
- Image placeholder parameter in `ImageLoader` methods [#486], [#494]
- `UIAppearance` conformance on custom properties of: [#489]
	- `FloatingTextField`
	- `FloatingTextFieldWithIcon`
	- `FloatingTextView`
	- `GrowingTextView`
- Navigation item title property to segmented controller [#491], [#493]
- `textInputBackgroundColor` property in `ColorTheme` [#492]
- Floating text view painter method in `ColorThemePainter` [#492]
- Floating text field background color set to `textInputBackgroundColor` in `CheetahColorThemePainter` [#492]


### Changed
- Set navigation bar and tab bar to be not translucent in `CheetahColorThemePainter` [#481]
- `imagePlaceholder` of `ImageLoader` to an instance property [#494]

### Removed
- `ColorThemeButtonStyle` to be less restrictive in theming buttons [#488]
- `UIImageView` extension method `setImage(from:, completion:)` [#486]

[#481]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/481
[#486]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/486
[#488]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/488
[#489]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/489
[#491]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/491
[#492]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/492
[#493]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/493
[#494]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/494
[UI-1.6.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/47?closed=1

## [UI-1.5.0] - 2020-08-10
### Added
- `NibViewController` back button customizability [#465]
- Cheetah theme dark mode [#466], [#472]
- Dependency to `CheetahLoyaltyUtils` [#471], [#475]


### Changed
- Number of lines to 0 of Message Label in Default Reload View Controller [#462]
- Utility code transferred to `CheetahLoyaltyUtils` [#471], [#475]

### Fixed
- Initializer visibility for subclasses of View Controllers [#473]
- Linter warnings [#468]

[#462]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/462
[#465]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/465
[#466]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/466
[#468]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/468
[#471]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/471
[#472]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/472
[#473]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/473
[#475]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/475
[UI-1.5.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/41?closed=1

## [UI-1.4.0] - 2020-07-20
### Added
- Added `WKWebView` delegate methods for decide policy for navigation response and action in `WebViewController` [#434]
- Added Navigation title for `StatefulViewController` set in `ContentController` [#439]
- `UIColor` extension methods for theme colors [#440]:
	- Text Input
	- Bar Item
	- Disabled Button
	- Highlighted Button
- Added deselect and displaying cell collection view delegate methods to be overrideable in `CollectionController` [#442]
- Added `TableController` and `TableViewController` [#443]
- Added button tint color and button style in `ColorTheme` [#447]

### Changed
- Moved `configureListCell` after setting the text style in `ListCollectionController` [#436]
- Set default disabled button color to light gray and default highlighted button color to primary [#433]
- Changed property names of List and Carousel Item Protocols to prevent conflict [#438]
- Updated Painter to use button tint color and button style [#447]
- Changed convenience init to designated and override designated inits in DetailViewController and StatefulViewController [#449]

### Removed
- Removed setting of segmented control color in `SegmentedViewController` [#441]

[#433]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/433
[#434]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/434
[#436]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/436
[#438]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/438
[#439]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/439
[#440]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/440
[#441]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/441
[#442]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/442
[#443]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/443
[#447]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/447
[#449]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/449
[UI-1.4.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/34?closed=1

## [UI-1.3.0] - 2020-06-16
### Added
- Added alert button text styles [#397]
- Added an extension method of `String` to create a period between two dates [#399]
- Added theming to the segement control of `SegmentedViewController` [#403], [#413]
- Added text theming to text field and text views [#402]
- Added error color in `ColorTheme` [#410]
- Added `didSet` for `isRefreshable` of `DetailViewController to set scroll view refresh control [#409]
- Added text theming for labels in cells [#408]
- Added button text theming [#412], [#422], [#424]
- Added bar item color themes [#416]
- Added method to set text theme for multiple elements [#418]

### Changed
- Added height constraint of 44 to the action button in `DetailViewController.xib` [#383]
- Change image picker error localizable string key to the generic error key [#400]

### Fixed
- Fixed access control level issues of the base init of `BaseCollectionController` [#373]
- Fixed showing of initial loading state of `StatefulViewController` [#374]
- Fixed typo in the protocol extension method `willChange(_ selectionButton: SelectionButton, isSelected: Bool) -> Bool` of `SelectionButtonDelegate` [#387]

### Removed
- Removed `NotificationHelper` to be moved into a separate Notifications SDK [#381], [#390]

[#373]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/373
[#374]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/374
[#381]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/381
[#383]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/383
[#387]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/387
[#390]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/390
[#397]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/397
[#399]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/399
[#400]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/400
[#402]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/402
[#403]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/403
[#408]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/408
[#409]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/409
[#410]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/410
[#412]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/412
[#413]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/413
[#416]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/416
[#418]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/418
[#422]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/422
[#424]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/424
[UI-1.3.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/26?closed=1

## [UI-1.2.1] - 2020-05-07
### Added
- Module Stability and XCFrameworks support [#354]
- Added pull down to refresh in `DetailViewController` [#351]
- Added detail image url in `DetailController` [#364]

### Changed
- Removed default text and adjust layout of `DetailViewController` [#348]
- Move setting up of `DetailViewController` to a separate method [#347]
- Changed access control of method `actionButtonPressed(_ sender: UIButton)` of `DetailViewController` to open and replaced *IBAction* association with *target-action* association in `setup` [#350]
- Implement all UISearchBarDelegate methods in BaseCollectionController to be overridable [#352]
- Change completion closure parameters of image loader to a `Result` object [#353]
- Set initial state of `StatefulViewController` to `loading` [#355]
- Color and Text Theming enhancement and fixes [#361], [#362], [#366]

[#347]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/347
[#348]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/348
[#350]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/350
[#351]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/351
[#352]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/352
[#353]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/353
[#354]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/354
[#355]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/355
[#361]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/361
[#362]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/362
[#364]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/364
[#366]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/366
[UI-1.2.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/22?closed=1

## [UI-1.2.0] - 2020-03-11
### Added
- Added `RatingButton` [#286]
- Added `DynamicListCollectionViewFlowLayout` [#290]
- Added `LoadingAlertViewController` [#289]
- Added generic localizable strings *"Done"*, *"No"*, *"Yes"* [#291]
- Added input type for `FloatingTextField` [#301]
- Added `SelectionButton` superclass for `CheckBox`, `RadioButton`, and `RatingButton` [#300]
- Added `ImageLoader` [#313]
- Added `nibName` class property in `NibViewController` [#326], [#338]
- Added overridable setup method in `NibViewController` [#335]

### Changed
- Used edited image instead of original image upon picking an image using `ImagePickerPresenter` [#276]
- Added editable parameter in `presentImagePicker` method in `ImagePickerPresenter` [#279]
- Added setting of default datePicker of `FloatingTextField` [#311]
- Consolidated custom `Notification` objects [#314]
- Changed implementation of `StatefulViewController` to be the content rather than holding a content view controller [#322]
- Changed implementation of `DetailViewController` to be able to present types that conform to `DetailPresentable` [#331, #336]
- Removed default implementation of the `refreshContent` method of `ContentController` protocol [#345]

### Fixed
- Fixed missing title of `FloatingTextField` when text is already set [#302]
- Fixed incorrect number of items when `ListCollectionController` is filtered [#333]
- Fixed bug on refreshing content on list collection [#345]

[#276]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/276
[#279]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/279
[#286]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/286
[#289]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/289
[#290]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/290
[#291]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/291
[#300]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/300
[#301]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/301
[#302]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/302
[#311]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/311
[#313]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/313
[#314]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/314
[#322]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/322
[#326]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/326
[#331]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/331
[#333]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/333
[#335]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/335
[#336]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/336
[#338]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/338
[#345]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/345
[UI-1.2.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/18?closed=1

## [UI-1.1.1] - 2019-12-18
### Added
- Added static variables for accessing theme colors in `UIColor` [#228]
- Added detail view controller labels: [#253]
	- `pointsLabel`
	- `periodLabel`
- Added `navigator` property to `CollectionController` protocol [#260]
- Added `showContentPage(id:)` method in `MessageNavigator` protocol [#268], [#270]

### Changed
- Changed `GrowingTextViewDelegate.willChangeHeight(_:, height:)` method to be optional. [#234]
- Change `Navigator` protocol to a class-only protocol [#260]

### Fixed
- `GrowingTextViewDelegate.didChangeHeight(_:, height:)` method will now be called only if needed. [#234]
- Remove setting of slStyle to views [#251]

[#270]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/270
[#268]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/268
[#260]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/260
[#253]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/253
[#251]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/251
[#234]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/234
[#228]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/228
[UI-1.1.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/11?closed=1

## [UI-1.1.0] - 2019-11-08
### Changed
- Built using Xcode 11 to support the iOS 13 SDK and Swift 5.1

### Fixed
- `AlertViewController` setting of presentation and transition style on initialization [#212]
- `FloatingTextFieldWithIcon` hold gesture press duration [#213]

[#212]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/212
[#213]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/213
[UI-1.1.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/9?closed=1

## [UI-1.0.2] - 2019-10-22
### Added
- AnalyticsLogger parameter keys as enum cases [#209]
- Theming support for `CheckBox` and `AlertViewController` [#203]

### Changed
- Remove required init `BaseCollectionController` [#208]
- `ThemeManager`'s `applyTheme` has the `theme` parameter with a default value of `currentTheme` [#203]

### Fixed
- Removed setting of `UIActivityIndicatorView` style in theming [#206]
- Unbalanced calls on presenting `AlertViewController` [#204]
- `CheetahTheme` primary and secondary colors [#203]
- `FloatingTextFieldWithIcon` component rects [#201]
- Text offset of `FloatingTextFieldWithIcon` is changed to a negative value after resigning responder [#195]
- Setting image of `FloatingTextFieldWithIcon` doesn't respect `templateImage` [#195]

[#209]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/209
[#208]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/208
[#206]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/206
[#204]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/204
[#203]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/203
[#201]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/201
[#195]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/195
[UI-1.0.2]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/7?closed=1

## [UI-1.0.1] - 2019-09-30
### Added
- Added Tests for Analytics [#182]
- Added `scheduleLocalNotification` static extension method for `UNUserNotificationCenter` [#185]
- Added `ThemeManager` support for the following: [#188]
	- `CheckBox`
	- `RadioButton`
	- `FloatingTextField`
	- `FloatingTextFieldWithIcon`
	- `GrowingTextView`
	- `FloatingTextView`
- Added Tests for MenuViewController [#189]
- Added `screenName` property in `StatefulViewController` with call to `logScreen` in `viewDidLoad` [#192]

### Fixed
- Added missing localized string values [#183]
- Added ListItemCell.xib to target [#190]
- Fixed tests for color assertions [#191]

### Changed
- Analytics Logger Protocol to changeless enum [#182]
- Modified selection and log out closures in `MenuCollectionController` to have a `MenuViewController` parameter [#189]
- Merged `eventName` and `parameters` in `logEvent` [#192]
- Changed `DetailController` to inherit from `ContentLoader` [#193]

### Removed
- Removed `scheduleLocalNotification` method from NotificationHelper protocol [#185]

[#182]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/182
[#183]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/183
[#185]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/185
[#188]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/188
[#189]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/189
[#190]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/190
[#191]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/191
[#192]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/192
[#193]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/pull/193
[UI-1.0.1]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/4?closed=1

## [UI-1.0.0] - 2019-09-09
### Added
- Added Base UI Components:
	- `NibViewController`
	- `StatefulViewController`
	- `CollectionViewController` for lists and carousel
	- `DetailViewController`
	- `SegmentedViewController`
	- `Navigator` protocol to navigate between view controllers
	- `MenuViewController`
	- `AppInfoViewController`
	- `CountriesCollectionController` to use with `CollectionViewController`
	- `StatesCollectionController` to use with `CollectionViewController`
	- `ImagePickerPresenter`
	- `WebViewController`
	- `ScannerViewController`
	- `AlertViewController`
	- `Localizer`
	- `CheckBox`
	- `RadioButton`
	- `FloatingTextField`
	- `FloatingTextFieldWithIcon`
	- `GrowingTextView`
	- `FloatingTextView`
	- `ThemeManager`

[UI-1.0.0]: https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/milestone/2?closed=1
