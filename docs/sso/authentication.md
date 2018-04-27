# Authentication Flow
## Implementing the SSO
The recommended flow for web applications where the client secret can be stored on a server is the Authorization Code Grant documented [here](http://tools.ietf.org/html/rfc6749#section-4.1).

For those that don't feel like reading the standard, the authentication is really just a series of HTTP requests and redirects described in this document.

## Redirect to the SSO
When a user clicks the login button on your website you need to redirect the user to `https://login.eveonline.com/oauth/authorize` with the following query string parameters:
- response_type: Must be set to "code".
- redirect_uri: After authentication the user will be redirected to this URL on your website. It must match the definition on file in the developers site.
- client_id: A string identifier for the client, provided by CCP.
- scope: The requested scopes as a space delimited string.
- state: An opaque value used by the client to maintain state between the request and callback. The SSO includes this value when redirecting back to the 3rd party website. While not required, it is important to use this for security reasons. [http://www.thread-safe.com/2014/05/the-correct-use-of-state-parameter-in.html](http://www.thread-safe.com/2014/05/the-correct-use-of-state-parameter-in.html) explains why the state parameter is needed.

Example URL: `https://login.eveonline.com/oauth/authorize/?response_type=code&redirect_uri=https%3A%2F%2F3rdpartysite.com%2Fcallback&client_id=3rdpartyClientId&scope=characterContactsRead%20characterContactsWrite&state=uniquestate123`

The user will need to log into their EVE Online account and select the character that your web site will be given access to. If the user is already logged in with an EVE Online account, they will just need to select a character and approve the required scopes.

The SSO will redirect the user back to the provided callback URL with an authorization code and the state as query string parameters.

Example URL: `https://3rdpartysite.com/callback?code=gEyuYF_rf...ofM0&state=uniquestate123`
- code: The Authorization code.
- state: The state parameter that was sent in the original request to the SSO.

## Verify the authorization code
At this point your website has the authorization code. The only thing the authorization code is good for is to obtain an access token.

It is also important to note that the authorization code is single use only, and has a lifetime of only five minutes.

You need to make a POST request to `https://login.eveonline.com/oauth/token` to exchange the authorization code for an access token. Example request:
```http
POST https://login.eveonline.com/oauth/token HTTP/1.1

Authorization: Basic bG9...ZXQ=
Content-Type: application/x-www-form-urlencoded
Host: login.eveonline.com

grant_type=authorization_code&code=gEyuYF_rf...ofM0
```
- Authorization HTTP header: [Basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) is used, with the client ID as the username and secret key as the password. The header should be the string "Basic " plus the [Base64](https://en.wikipedia.org/wiki/Base64) encoded string `{client_id}:{client_secret}`.
    - It is very important to make sure there is no whitespace around or in the string that is being Base64 encoded. If in doubt, try to Base64 encode the sample values provided below and compare them to the results:
        - Example client ID: `3rdparty_clientid`
        - Example secret key: `jkfopwkmif90e0womkepowe9irkjo3p9mkfwe`
        - Concatenated to become: `3rdparty_clientid:jkfopwkmif90e0womkepowe9irkjo3p9mkfwe`
        - Base64 encoded to: `M3JkcGFydHlfY2xpZW50aWQ6amtmb3B3a21pZjkwZTB3b21rZXBvd2U5aXJram8zcDlta2Z3ZQ==`
        - Resulting in the Authorization header: `Basic M3JkcGFydHlfY2xpZW50aWQ6amtmb3B3a21pZjkwZTB3b21rZXBvd2U5aXJram8zcDlta2Z3ZQ==`
- grant_type: Must be set to "authorization_code".
- code: The authorization code obtained earlier.

Alternatively, while not in accordance with the OAuth 2.0 standard, the body of the request may use JSON encoding. Example:
```http
POST https://login.eveonline.com/oauth/token HTTP/1.1

Authorization: Basic bG9...ZXQ=
Content-Type: application/json
Host: login.eveonline.com

{
  "grant_type":"authorization_code",
  "code":"gEyuYF_rf...ofM0"
}
```

A successful verification request will yield a response containing details about the access token. Example:
```json
{
    "access_token":"uNEEh...a_WpiaA2",
    "token_type":"Bearer",
    "expires_in":1200,
    "refresh_token":"gEy...fM0"
}
```
