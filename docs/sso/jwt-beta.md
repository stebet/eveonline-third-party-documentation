# PRERELEASE - JWT Tokens

## WARNING - READ THIS
Currently the JWT tokens are in pre-release stage. Feel free to try them out but be aware that there are certainly bugs. They might work and they might not.

## Index
* [Why JWT tokens?](#why-jwt-tokens)
* [What's new](#whats-new)
* [Getting started](#getting-started)
  * [Implicit grant](#implicit-grant)

## Why JWT tokens?
Several reasons, here are some of the benefits.
* Self-contained
  * Your apps can look at the token, see when it expires and just refresh-on-demand, instead of having to check first if the token is still valid
   or retrying if you get a 401.
  * Reduced data storage for the EVE SSO, better performance and overall making CCP Ghostrider and the CCP DBAs happy
* Cryptographically signed
  * This means that services like ESI can validate the tokens without talking to the EVE SSO, improving performance for everyone since there are fewer network round-trips.
* Extensible
  * Since JWT tokens contains standard claims about the authorized party, they can be extended without breaking existing clients.
* Standards-based
  * There are tons of libraries out there for almost every programming language to work with JWT tokens.

## What's new?
Our JWT implementation is a lot better in many ways than the legacy token implementation. It's still a work in progress, but here are the highlights so far:
* [OAuth Discovery](https://tools.ietf.org/html/draft-ietf-oauth-discovery-10) based
* [OAuth PKCE](https://tools.ietf.org/html/rfc7636) support
* [JWT Profile for OAuth 2.0 Client Authentication](https://tools.ietf.org/html/rfc7523) support
* Supports adding new scopes to existing authorizations grants (eliminates duplicates).
* Supports migrating legacy refresh tokens to the new OAuth refresh tokens.
* Supports JWT client authorization.

## Getting started

1. ### Implicit grant (no refresh token)
The implicit grant allows you to fetch a token for browser-based applications by getting the access token as part of the URL fragment (anything after the # sign).
That means you can go through the OAuth flow entirely in a browsers for example.
