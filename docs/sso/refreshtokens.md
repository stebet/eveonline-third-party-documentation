# Refresh Tokens
If any valid scope was requested in the initial redirect to the SSO, a refresh token will be returned by the token endpoint, along with the access token. While the access token will expire after the listed interval, the refresh token can be stored and used indefinitely. Users can revoke access for individual apps on the [support site](https://community.eveonline.com/support/third-party-applications/).

To get a new access token you must make a POST request to `https://login.eveonline.com/oauth/token` with the following parameters:
- grant_type: Must be set to "refresh_token".
- refresh_token: The refresh token received from the last request to the token endpoint.

You also need to include the same Authentication header ([basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) with the client ID as the username and secret key as the password) which was used for previous requests to the token endpoint.

The request should look like this:
```http
POST https://login.eveonline.com/oauth/token HTTP/1.1

Authorization: Basic bG9...ZXQ=
Content-Type: application/x-www-form-urlencoded
Host: login.eveonline.com

grant_type=refresh_token&refresh_token=gEy...fM0
```

Currently, it also works to post the body of the request as JSON:
> Please note that using JSON is NOT recommended as it is not in accordance with the spec and may break at any moment. You have been warned!
> -CCP Ghostrider

```http
POST https://login.eveonline.com/oauth/token HTTP/1.1

Authorization: Basic bG9...ZXQ=
Content-Type: application/json
Host: login.eveonline.com

{
  "grant_type":"refresh_token",
  "refresh_token":"gEy...fM0"
}
```



The response should contain details about the new access token for that user. Example:
```json
{
  "access_token":"MXP...tg2",
  "token_type":"Bearer",
  "expires_in":1200,
  "refresh_token":"gEy...fM0"
}
```
