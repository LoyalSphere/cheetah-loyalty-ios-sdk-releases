# Cheetah Loyalty Core iOS

- [Requirements](#requirements)
- [Installation](#installation)
	* [Cocoapods](#cocoapods)
	* [Manually](#manually)
- [Usage](#usage)
	* [Configuration](#configuration)
	* [Authentication](#authentication)
		+ [Signing Up](#signing-up)
		+ [Logging In](#logging-in)
		+ [Logging In with Social Netorks](#logging-in-with-social-networks)
		+ [Refreshing Access Token Manually](#refreshing-access-token-manually)
		+ [Logging Out](#logging-out)
	* [Basics](#basics)
		+ [Sending Requests](#sending-requests)
		+ [Handling Responses](#handling-responses)
		+ [Fetching Lists](#fetching-lists)
			- [Fetching List of Nearby Places](#fetching-list-of-nearby-places)
		+ [Fetching Detail](#fetching-detail)
	* [Push Notifications](#push-notifications)
		+ [Registering Device](#registering-device)
		+ [Tracking a Message](#tracking-a-message)
	* [Respondable Objects](#respondable-objects)
		+ [Responding to a Challenge](#responding-to-a-challenge)
		+ [Responding to an Offer](#responding-to-an-offer)
       + [Responding to a Reward](#responding-to-a-reward)
	* [Clipping or Unclipping an Offer](#clipping-or-unclipping-an-offer)
	* [Submitting Feedback](#submitting-feedback)


## Requirements
* Deployment Target: iOS 11.0
* Xcode 11.x
* Swift 5.1
* `CheetahLoyaltyUtils` v1.0.0

## Installation

### Cocoapods

1. Open a terminal window then add the private podspec repo to the Cocoapods installation by entering the following:

```sh
pod repo add CheetahLoyaltySDK https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git
```

2. Add a source for the CheetahLoyaltySDK and add the `CheetahLoyaltyCore` pod in your podfile:

```ruby
platform :ios, '11.0'

source 'https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk-podspecs.git'
source 'https://github.com/CocoaPods/Specs.git'

target '<YourApp>' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

  pod 'CheetahLoyaltyCore'
end
```

3. Open a terminal window to where your project and podfile is located and run the following to install the pod:

```sh
pod install
```

### Manually

1. Install [`CheetahLoyaltyUtils`](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/blob/master/CheetahLoyaltyUtils/README.md) framework.
2. [Download the CheetahLoyaltyCore SDK from the releases](https://github.com/LoyalSphere/cheetah-loyalty-ios-sdk/releases).
3. Extract it then drag & drop CheetahLoyaltyCore.xcframework to your project's directory.
4. In "Frameworks, Libraries, and Embedded Content" section under the "General" tab, click on the "+" button then "Add Other", and then "Add Files...".
5. Select the CheetahLoyaltyCore.xcframework file and make sure that it is set to "Embed & Sign" in the "Embed" column in the "Frameworks, Libraries, and Embedded Content" section under the "General" tab.

## Usage

### Configuration
Before using the Cheetah Loyalty Core framework, a configuration file is needed to determine the settings it needs upon sending requests. The configuration file is a *plist* named **CheetahLoyalty-Info**. The file is to be included in the project bundle.

The primary contents of this **CheetahLoyalty-Info.plist** are as follows:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>BUSINESS_UNIT</key>
	<string>SwiftSDKBusinessUnit</string>
	<key>USER_AGENT_NAME</key>
	<string>SwiftSDK</string>
	<key>CLIENT_ID</key>
	<string><your_client_id></string>
	<key>CLIENT_SECRET</key>
	<string><your_client_secret></string>
	<key>CLIENT_URL</key>
	<string><your_client_url></string>
	<key>METRIC</key>
	<string><your_metric></string>
	<key>GEOFENCING_ENABLED</key>
	<true/>
	<key>ACCESS_TOKEN_EXTERNAL</key>
	<false/>
</dict>
</plist>
```

The key used in the **CheetahLoyalty-Info.plist** are:

* `BUSINESS_UNIT` - String indicating the business unit.
* `USER_AGENT_NAME` - The user agent name to be used in the header of requests.
* `CLIENT_ID` - The API KEY for the Loyalty API
* `CLIENT_SECRET` - The API SECRET KEY for the Loyalty API
* `CLIENT_URL` - The URL of the Loyalty API gateway
* `METRIC` - The API metric
* `GEOFENCING_ENABLED` - Boolean flag that indicates whether geofencing is enabled
* `ACCESS_TOKEN_EXTERNAL` - Boolean flag that indicates whether the access token is from an external source

Some of these values can be found in the console of the environment the app is going to use.

### Authentication

#### Signing Up
Create a new user by calling `AuthenticationAPI.signUp` method like so:

```swift
let parameters: [String: Any] = [
	"first_name": "Irene",
	"last_name": "Adler",
	"email": "ireneadler@gmail.com",
	"password": "IAmSherlocked",
	"password_confirmation": "IAmSherlocked"
]

AuthenticationAPI.signUp(with: parameters, completion: { result in
	switch result {
	case .success:
		// Handle successful sign up
	case .failure:
		// Handle error
	}
}
```
The parameters used in this request is the most commonly used for sign up. The usage of each parameter is as follows:

|Parameter Name|Usage|
|---|---|
|*first_name*| User's given name |
|*last_name*| User's last name |
|*email*| User's email address |
|*password*| User's password to be used when logging in |
|*password_confirmation*| Used for comparison to ensure that the given password is correct |
|*referral_code*| (Optional) If provided and valid, will link referral to member that shared the code |

> **IMPORTANT**:
> Depending on your configuration of member attributes in the console, some fields could be mandatory.
> For example, you can require fields like `card_id` and `birthdate` but not `mobile_phone`

Take note that this call will fail if:

* Any of the required parameters are empty or inexistent
* The `email` is invalid
* The `email` is already used
* The `password` and `password_confirmation` are less than 8 characters
* The `password` and `password_confirmation` doesn't match

#### Logging In
Most of the Loyalty API requests requires an access token to be accessed. The access token can be created/retrieved by logging in the user. Login the user using the `AuthenticationAPI`:


1. First, import the `CheetahLoyaltyCore`.

    ```swift
	import CheetahLoyaltyCore
	```

2. Then login using one of the `AuthenticationAPI` login methods.
	
	```swift
	AuthenticationAPI.logIn(email: email, password: password) { (result) in
		switch result {
	    case .success(let response):
	        // Login successful
	    case .failure(let error):
	        // Login failure
	    }
	}
	```
	The access token is automatically saved and refreshed when needed.
	
	
#### Logging In with Social Networks
Logging in with *social networks* can also be achieved in `AuthenticationAPI` by providing the *access token* from the *social network* and setting the login type:

```swift
let accessToken = "<The social network access token>"
AuthenticationAPI.logIn(socialNetwork: .facebook, accessToken: accessToken, completion: { (result) in
	switch result {
    case .success(let apiResponse):
    	// Login successful
    case .failure(let error):
        // Loging failure
    }
})
```

The socialNetwork parameter is an enum with members: `apple, facebook, google, twitter, linkedin`.

#### Refreshing Access Token Manually
Refreshing the access token is automatically handled. But if needed, to manually refresh the access token:

```swift
let refreshToken = "<The refresh token>"
AuthenticationAPI.refreshToken(refreshToken: refreshToken, completion: { (result) in
	switch result {
	case .success(let apiResponse):
		// Refresh successful
	case .failure(let error):
		// Refresh failure
	}
})
```

When a request responds with an *expired token* error, the SDK will attempt to refresh the access token automatically and attempt to retry the request again. However if there is no refresh token set, the request will just respond with the error.

#### Logging Out
To log out the user:

```swift
let accessToken = "<The access token of the user>"
AuthenticationAPI.logOut(accessToken: accessToken) { (result) in
	switch result {
    case .success(let response):
        // Logout successful
    case .failure(let error):
        // Logout failure
    }
}
```

When a request responds with an error namely *missing token*, *invalid token*, and *revoked token*, a notification named `APIAccessTokenDidBecomeInvalid` is posted which can then be observed using the `NotificationCenter`. This usually indicates that the user needs to be logged out of the application.

### Basics
#### Sending Requests
API requests are classified by module. Each API module have methods to send requests.

For example, *Activity* related requests can be found in the `ActivitiesAPI` type.  
To get all activities of the user:

```swift
ActivitiesAPI.getActivities(with: nil) { (result) in
   // Handle request result
	switch result {
    case .success(let apiResponse):
        // Show activities list
    case .failure(let error):
        // Show error
    }
}
```

#### Handling Responses
All API request completion closures have a `Result` type as a parameter. `Result` types as explained [here](https://developer.apple.com/documentation/swift/result), carry two object types for success and failure where the failure type conforms to the [`Error`](https://developer.apple.com/documentation/swift/error) protocol.  

In the Cheetah Loyalty Core framework, the success type is an `APIResponse`.  
The `APIResponse` consists of:

* `request` - The URL request sent to the server.
* `data` - The data returned by the server.
* `response` - The server's response to the URL request.
* `value` - The associated value of the response from the server. This is the model retrieved from the response. The type of this value depends on the request.
* `listInfo` - A `ListInfo` object representing list information of a request returning a list of values. If the request did not return a list of values, this is nil.

The model from a request's response can be accessed through the `value` property of the `APIResponse` object like so:

```swift
	case .success(let response):
		let authenticationInfo = response.value
```

The failure type which is an `Error` can be retrieved similarly:

```swift
	case .failure(let error):
		let authenticationError = error
```

### Checking for version upgrades

To check if the application is in need of a version upgrade, it needs to call the `UpgradeCheckAPI.getUpgradeCheck` like so:

```swift
UpgradeCheckAPI.getUpgradeCheck(with: nil,
                                completion: { result in
                                    switch result {
                                    case .success(let apiResponse):
                                        let upgradeCheck = apiResponse.value
                                        // Handle upgrade check
                                    case .failure(let error):
                                        // Show error
                                    }
})

```

This API call will return an `UpgradeCheck` object, that has a property of `upgradeAction` that could have a value of either `requiredUpgrade` or `suggestedUpgrade`.

Where this will be called depends on the application requirement. It is recommended to call this in the *applicationDidBecomeActive:* method of *UIApplicationDelegate*.

### Fetching Lists
Objects from the Loyalty API can be fetched into lists. These lists can be customized to be fetched by page with a specified number of items per page, object layout, and sorted.

For example, to fetch a list of rewards:

```swift
RewardsAPI.getRewards(with: ["page": currentPage + 1,
                             "per_page": 15,
                             "layout": "mobile_list",
                             "sort_by": "publish_date",
                             "sort_dir": "desc"],
                      showFavorites: false,
                      completion: { (result) in
                        // Handle request result
                        switch result {
                        case .success(let apiResponse):
                            let rewards = apiResponse.value
                            // Show rewards list
                        case .failure(let error):
                            // Show error
                        }
})
```

The parameters used in this request is the most commonly used to fetch lists. The usage of each parameter is as follows:

|Parameter Name|Usage|
|---|---|
|*page*| The page of the list to fetch|
|*per_page*| The number of object to fetch in a page|
|*layout*| The layout of the objects in the list depending on the admin console configuration.
|*sort_by*| The object property to sort the list
|*sort_dir*| The sort direction basing on the sort option specified by the value passed in *sort_by*. This can either be ***desc*** for descending, and ***asc*** for ascending

#### Fetching List of Nearby Places

To fech a list of nearby places from a given coordinate:

```swift
let parameters: Parameters = [
    "lat": 14.581776,
    "lon": 120.977019,
    "distance": 100,
    "unit": "km"
]

PlacesAPI.getPlacesNearby(with: parameters,
                          completion: { result in
                            switch result {
                            case .success(let apiResponse):
                                let nearbyPlaces = apiResponse.value
                                // Handle nearby places
                            case .failure(let error):
                                // Show error
                            }
})
```

The parameters used in this request is the most commonly used to fetch nearby places. The usage of each parameter is as follows:

|Parameter Name|Usage|
|---|---|
|*lat*| Coordinate's latitude |
|*lon*| Coordinate's longitude |
|*distance*| The search radius. Default is ***20*** |
|*unit*| The unit for the search radius. Values are ***m***, ***km***, ***mi***, and ***ft***. Default is ***mi*** |

### Fetching Detail
Objects from the Loyalty API can have its details fetched. Each object will have a designated identifier for its specific type which will be used to specify what object detail to fetch. A layout can also be specified for the detail fetched. The layout of the object detail will depend on what is configured in the admin console.

For example, to fetch a specific reward:

```swift
RewardsAPI.getReward(id: 2,
                     with: ["layout": "mobile_detail"],
                     completion: { result in
                     	 // Handle request result
                        switch result {
                        case .success(let apiResponse):
                        	let reward = apiResponse.value
                            // Show reward detail
                        case .failure(let error):
                            // Show error
                        }
})
```

### Push Notifications
#### Registering device
In order for a user's device to receive push notifications from the loyalty server, the device must be setup to receive push notifications and registered to the Loyalty API . The user's device is registered by sending the device token to the Loyalty API.

Upon setting up of the device to receive push notifications, register the user's device to the Loyalty API:

```swift
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
    DevicesAPI.registerDevice(deviceToken: deviceToken.hexString, 
    						  deviceID: UUID().uuidString, 
    						  completion: { (response) in
    switch response {
        case .success:
            // Handle register success
        case .failure:
            // Handle error
        }
    })
}
```

#### Tracking a Message
Push notificaions are recognized as *Messages* in the loyalty server. Tracking a message will mark it *opened*. Track a message by calling `MessagesAPI.trackMessage` and passing the ***message ID*** like so:

```swift
MessagesAPI.trackMessage(id: "1", completion: { result in
	switch result {
    case .success(let apiResponse):
    	// Message tracking successful
    case .failure(let error):
        // Handle Error
    }
}
```

### Respondable Objects
Some objects such as *Offer*, *Challenge* and *Reward* can be responded to. Responding to an object initiates an action associated to that object. Successfully responding to an object gives a response info object relating to it.

#### Responding to a Challenge
Challenge objects can be responded for a user to receive a prize. There are three ways to respond on the challenge depending on the content to respond with. When responding to a challenge, a `Challenge.ResponseInfo` is returned containing information on the status of challenge response. If responding to the challenge fails, an error is returned.

1. To respond to a challenge with text:

	```swift
	let parameters = ["answer[text]": "My answer"]
	
	ChallengesAPI.respondToChallenge(id: challenge.id,
	                                 with: parameters,
	                                 completion: { result in
					                     	// Handle request result
					                        switch result {
					                        case .success(let apiResponse):
					                            let responseInfo = apiResponse.value
					                            // Handle Challenge Response Info
					                        case .failure(let error):
					                            // Show error
					                        }
	})
	
	```
	
	The *answer[text]* parameter accepts a string that will be used to respond to the challenge.

2. To respond to a challenge with an image:

	```swift
	let image = UIImage(named: "ImageAnswer")
	let parameters = ["answer[text]": "My answer"]
	
	ChallengesAPI.respondToChallengeWithImage(id: challenge.id,
												     image: image
				                                with: parameters,
				                                completion: { result in
								                   	  // Handle request result
								                     switch result {
								                     case .success(let apiResponse):
								                     	let responseInfo = apiResponse.value
								                        // Handle Challenge Response Info
								                     case .failure(let error):
								                        // Show error
								                     }
	})
	
	```
	
	The *answer[text]* parameter still accepts a string that will additionally be used to respond to the challenge.
	
3. To respond to a challenge with a video:

	```swift
	let videoUrl = UIImage(named: "ImageAnswer")
	let parameters = ["answer[text]": "My answer"]
	
	ChallengesAPI.respondToChallengeWithVideo(id: challenge.id,
												     videoUrl: videoUrl
				                                with: parameters,
				                                completion: { result in
								                   	// Handle request result
								                     switch result {
								                     case .success(let apiResponse):
								                     	let responseInfo = apiResponse.value
								                        // Handle Challenge Response Info
								                     case .failure(let error):
								                        // Show error
								                     }
	})
	
	```
	
	The *answer[text]* parameter still accepts a string that will additionally be used to respond to the challenge.
	
#### Responding to an Offer
To respond to an offer, provide the id of the offer like in the example below:

```swift
let id = 1
OffersAPI.respondToOffer(id: id, completion: { (result) in
	switch result {
   	case .success(let apiResponse):
		// Handle Offer Response Info
   	case .failure(let error):
   		// Show error
    }
})
```

#### Responding to a Reward
Reward objects can be responded for a user to redeem a reward. There are three ways to respond on the reward depending on the content to respond with. When responding to a reward, a `Reward.ResponseInfo` is returned containing information on the status of the reward response. If redeeming a reward fails, an error is returned.

1. To respond to a reward:

	```swift
	RewardsAPI.redeemReward(id: 249,
                                awardId: nil,
                                address: [
                                    "street_address": "221B Baker",
                                    "city": "London"
                                ],
                                parameter: ["combination_id": "reward_combination_id"],
                                isResponse: true) { [unowned self] (result) in
                                    // Handle request result
                                    switch result {
                                    case .success(let apiResponse):
                                        let responseInfo = apiResponse.value
                                    // Handle Reward Response Info
                                    case .failure(let error):
                                        // Show error
                                    }
        }
	
	```
	If you are giving a reward of type `award` to the user, just provide the award ID in the parameter supplied.
	
	Here are the available keys for the address:
	
	|Keys|Usage|
|---|---|
|*first_name*| First name of the user|
|*last_name*| Last name of the user|
|*street_address*| Street address of the user|
|*street_address2*| Street address 2 of the user|
|*city*| City of the user|
|*state*| State of the user|
|*zip_code*| Zip Code of the user|
|*country_code*| Country Code of the user|
|*phone_number*| Phone Number of the user|

2. To respond to a reward of type certificate / coupon / embedded challenge:

	```swift
	RewardsAPI.redeemReward(id: 249,
                                awardId: nil,
                                address: nil,
                                isResponse: true) { [unowned self] (result) in
                                    // Handle request result
                                    switch result {
                                    case .success(let apiResponse):
                                        let responseInfo = apiResponse.value
                                    // Handle Reward Response Info
                                    case .failure(let error):
                                        // Show error
                                    }
        }
	
	```
	
	Just take note of the returned `Reward.ResponseInfo` since this will provide you with what present your users whether if it is a `Coupon`, a `Certificate` or an `embedded` Challenge.

### Clipping or Unclipping an Offer
Clipping an offer marks it for use while unclipping removes this from an existing clipped *Offer*.

1. Clipping an offer will create an offer response with *processing_status = clipped* 

	```
	SLOffersAPI.clipOffer(id: offer.id, completion: { (response)
		switch response {
		case .success (let apiResponse):
			//Successfully clipped the offer
		case .failure(let error):
			//Failed to clip the offer
		}
	})	
	```
	
2. Unclipping an offer will change the offer response *processing_status* to *cancelled* 

	```
	SLOffersAPI.unclipOffer(id: offer.id, completion: { (response)
		switch response {
		case .success (let apiResponse):
			//Successfully unclipped the offer
		case .failure(let error):
			//Failed to unclip the offer
		}
	})	
	```

### Submitting Feedback
Use `FeedbacksAPI` for submitting feedback with *subject* and *body*:

```swift
let subject = "Subject"
let body = "Body"
FeedbacksAPI.sendFeedback(subject: subject, body: body, completion: { (result) in
	switch result {
 	case .success(let apiResponse):
    	// Submit feedback successful
    case .failure(let error):
      	// Submit feedback failure
    }
})
```

Alternatively `FeedbacksAPI` has another method for submitting feedback:

```swift
let subject = "Subject"
let body = "Body"
let category = "sample category"
var params: [String: Any] {
	return ["subject": subject,
            "body": body,
            "category": category]
        }
        
FeedbacksAPI.submitFeedback(with: params, completion: { (result) in
	switch result {
	case .success(let apiResponse):
    	// Submit feedback successful
  	case .failure(let error):
    	// Submit feedback failure
    }
})
```

There are additional parameters that can also be use:

|Parameter Name|Usage|
|---|---|
|*email*| Email of the user|
|*first_name*| First name of the user|
|*last_name*| Last name of the user|

**Note:** Use the parameters above for sending feedback if there is no user logged in (e.g. if user is a guest and doesn't have an account yet).

## More
For more detailed information about our SDK, please contact the Cheetah Digital Loyalty team.
