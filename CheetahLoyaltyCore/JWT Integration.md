# Cheetah Loyaty Core iOS JWT Integration

- [Requirements](#requirements)
- [JWT Integration](#usage)

## Requirements
* Deployment Target: iOS 11.0
* Xcode 11.x
* Swift 5.1
* CheetahLoyaltyCore 1.1.2

## JWT Integration
Integrating the Cheetah Loyalty Core with JWT (*JSON Web Token*) requires the access token to be handled manually. The JWT acts as the access token for the API and can be treated as such. Expired token errors must be relayed to the token provider. Other errors must be handled as needed.

### Setting the JWT
After retrieving the JWT from the token provider, it can now be set as the access token of the Cheetah Loyalty Core `API`.

```swift
let jwt = "<my_jwt>"
API.shared.setCredentials(jwt)
```

### Access Token Errors
While accessing the loyalty API, a number of access token errors may be encountered.

#### Expired Token Error (4002)
This error is encountered when the current token passed in the request has expired. In using JWT, requests with this error will not be handled automatically since the token provider has the refresh token. The request will then result in a failure with an *expired token* error. Upon encountering this error, the application must communicate with the token provider to retrieve a new JWT. The new JWT must then be set in the `API`. Once this is done, the request can be retried with the new JWT.

#### Missing Token Error (4000)
This error is produced by not having an access token in the request.

#### Invalid Token Error (4001)
This error is produced when the access token in the request is invalid or incorrect.

#### Revoked Token Error (4003)
This error is produced when the access token has been revoked in the loyalty server.

When a request responds with an error namely *missing token*, *invalid token*, and *revoked token*, a notification named `APIAccessTokenDidBecomeInvalid` is posted which can then be observed using the `NotificationCenter`. This usually indicates that the user needs to be logged out of the application.

## More
For more detailed information about our SDK please see the [Cheetah Loyalty Core README.md] or please contact the Cheetah Digital Loyalty team.

[Cheetah Loyalty Core README.md]: (README.md)