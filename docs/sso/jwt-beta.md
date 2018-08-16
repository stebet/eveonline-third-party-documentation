# BETA - JWT Authentication Flow

>## **Please note**: This is documentation for a prerelease feature and is subject to change

## Implementing the SSO

The recommended flow for all applications tat required refresh tokens is to use the Authorization Code Grant flow with PKCE. The Authorization Code Grant is documented [here](https://tools.ietf.org/html/rfc6749#section-4.1) and the PKCE additions are documents [here](https://tools.ietf.org/html/rfc7636).

For those that don't feel like reading the standard, the authentication is really just a series of HTTP requests and redirects described in this document.

## Redirect to the SSO

When a user clicks the login button on your website you need to redirect the user to `https://login.eveonline.com/v2/oauth/authorize` with the following query string parameters:

- response_type: Must be set to "code".
- redirect_uri: After authentication the user will be redirected to this URL on your website. It must match the definition on file in the developers site.
- client_id: A string identifier for the client, provided by CCP.
- scope: The requested scopes as a space delimited string.
- state: An opaque value used by the client to maintain state between the request and callback. The SSO includes this value when redirecting back to the 3rd party website. While not required, it is important to use this for security reasons.
- code_challenge: The code challenge, a SHA1 hash of the generated code verifier, as described [here](https://tools.ietf.org/html/rfc7636#section-4). This is optional, but highly recommended. **If provided, your application will be able to get a refresh token without providing the client secret.**
- code_challenge_method: Set to `S256`

[http://www.thread-safe.com/2014/05/the-correct-use-of-state-parameter-in.html](http://www.thread-safe.com/2014/05/the-correct-use-of-state-parameter-in.html) explains why the state parameter is needed.

The PKCE RFC explains in Appendix B how the code verifier works. Here is an excerpt from the spec.

>The client uses output of a suitable random number generator to create a 32-octet sequence.  The octets representing the value in this example (using JSON array notation) are:
>
>`[116, 24, 223, 180, 151, 153, 224, 37, 79, 250, 96, 125, 216, 173, 187, 186, 22, 212, 37, 77, 105, 214, 191, 240, 91, 88, 5, 88, 83, 132, 141, 121]`
>
>Encoding this octet sequence as base64url provides the value of the code_verifier:
>
>`dBjftJeZ4CVP-mB92K27uhbUJU1p1r_wW1gFWFOEjXk`
>
>The code_verifier is then hashed via the SHA256 hash function to produce:
>
>`[19, 211, 30, 150, 26, 26, 216, 236, 47, 22, 177, 12, 76, 152, 46, 8, 118, 168, 120, 173, 109, 241, 68, 86, 110, 225, 137, 74, 203, 112, 249, 195]`
>
>Encoding this octet sequence as base64url provides the value of the code_challenge:
>
>`E9Melhoa2OwvFrEMTJguCHaoeK1t8URWbuGJSstw-cM`
>
>The authorization request includes:
>
>`code_challenge=E9Melhoa2OwvFrEMTJguCHaoeK1t8URWbuGJSstw-cM&code_challenge_method=S256`
>
>The authorization server then records the code_challenge and code_challenge_method along with the code that is granted to the client.

Example URL: `https://login.eveonline.com/v2/oauth/authorize/?response_type=code&redirect_uri=https%3A%2F%2F3rdpartysite.com%2Fcallback&client_id=3rdpartyClientId&scope=characterContactsRead%20characterContactsWrite&state=uniquestate123&code_challenge=E9Melhoa2OwvFrEMTJguCHaoeK1t8URWbuGJSstw-cM&code_challenge_method=S256`

The user will need to log into their EVE Online account and select the character that your web site will be given access to. If the user is already logged in with an EVE Online account, they will just need to select a character and approve the required scopes.

The SSO will redirect the user back to the provided callback URL with an authorization code and the state as query string parameters.

Example URL: `https://3rdpartysite.com/callback?code=gEyuYF_rf...ofM0&state=uniquestate123`

- code: The Authorization code.
- state: The state parameter that was sent in the original request to the SSO.

## Verify the authorization code

At this point your website has the authorization code. The only thing the authorization code is good for is to obtain an access token.

It is also important to note that the authorization code is single use only, and has a lifetime of only five minutes. To complete the token flow you'll also need to provide the code verifier.

You need to make a POST request to `https://login.eveonline.com/v2/oauth/token` to exchange the authorization code for an access token. Example request:

```http
POST https://login.eveonline.com/oauth/token HTTP/1.1

Content-Type: application/x-www-form-urlencoded
Host: login.eveonline.com

grant_type=authorization_code&client_id=3rdpartyClientId&code=gEyuYF_rf...ofM0&code_verifier=dBjftJeZ4CVP-mB92K27uhbUJU1p1r_wW1gFWFOEjXk
```

- grant_type: Must be set to "authorization_code".
- client_id: A string identifier for the client, provided by CCP.
- code: The authorization code obtained earlier.
- code_verifier: The unhashed code verifier that was generated for the authorization.

A successful verification request will yield a response containing details about the access token. Example:

```json
{
    "access_token":"uNEEh...a_WpiaA2",
    "token_type":"Bearer",
    "expires_in":1200,
    "refresh_token":"gEy...fM0"
}
```
