# Token Revocation
## Implementing the revocation process

You need to make a POST request to `https://login.eveonline.com/oauth/revoke` to revoke an access_token or a refresh_token. Example request:
```http
POST https://login.eveonline.com/oauth/revoke HTTP/1.1

Authorization: Basic bG9...ZXQ=
Content-Type: application/x-www-form-urlencoded
Host: login.eveonline.com

token_type_hint=access_token&token=gEyuYF_rf...ofM0
```
- Authorization HTTP header: [Basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication) is used, with the client ID as the username and secret key as the password. The header should be the string "Basic " plus the [Base64](https://en.wikipedia.org/wiki/Base64) encoded string `{client_id}:{client_secret}`.
    - It is very important to make sure there is no whitespace around or in the string that is being Base64 encoded. If in doubt, try to Base64 encode the sample values provided below and compare them to the results:
        - Example client ID: `3rdparty_clientid`
        - Example secret key: `jkfopwkmif90e0womkepowe9irkjo3p9mkfwe`
        - Concatenated to become: `3rdparty_clientid:jkfopwkmif90e0womkepowe9irkjo3p9mkfwe`
        - Base64 encoded to: `M3JkcGFydHlfY2xpZW50aWQ6amtmb3B3a21pZjkwZTB3b21rZXBvd2U5aXJram8zcDlta2Z3ZQ==`
        - Resulting in the Authorization header: `Basic M3JkcGFydHlfY2xpZW50aWQ6amtmb3B3a21pZjkwZTB3b21rZXBvd2U5aXJram8zcDlta2Z3ZQ==`
- token_type_hint: Is optional, should contain the type of the token (for example access_token or refresh_token).
- token: The token to revoke.

Alternatively, while not in accordance with the OAuth 2.0 standard, the body of the request may use JSON encoding. Example:
```http
POST https://login.eveonline.com/oauth/revoke HTTP/1.1

Authorization: Basic bG9...ZXQ=
Content-Type: application/json
Host: login.eveonline.com

{
  "token_type_hint":"access_token",
  "token":"gEyuYF_rf...ofM0"
}
```

The server replies with a HTTP 200 if the revocation has been successful or if the client submitted an invalid token.
