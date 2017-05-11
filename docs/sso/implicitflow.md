# SSO For Browser Apps

From the perspective of OAuth2 based authentication, browser applications
 can be broken into two main categories based on where they communicate with
 the protected resources (In the case of EVE SSO, the protected resource
 is [ESI](../esi/index.md)). These categories can be broadly classed as Client
 side and Server side.

Client Side applications will communicate with the protected resource from
 the web browser, as such the authentication details never need to be shared
 with the server.

Server Side applications perform the communication with the protected
 resources on the web server. In this case the client doesn't need to know
 about the authentication details.

The distinction between client and server side applications is important as
 it helps inform on the best OAuth2 authentication workflow to use,

## Client Side Applications

In most situations, Client side applications will want use the Implicit Flow.
 The primary reason this is preferred for client side applications is that it
 avoids exposing the client secret. It also has the added benefit of reducing
 the number of steps required to get a usable token.

Using the implicit workflow is very easy - you simply redirect the user to the
 authorization endpoint, including your `client_id`, `redirect_uri` and setting
 `response_type` to `token`

It should be noted that the EVE SSO implementation of the OAuth2 Implicit flow
 appends the token object as a URL hash component, So it will not been seen by
 the server without the client explicitly passing it along.

## Server Side Applications

Server side applications should always use the authorization code flow. Using
 the authorization code flow avoids exposing your authorization token to
 more than is necessary as the client side will only see the access code.

The Authorization code flow has the added benefit of being able to contain a
 `refresh_token` which can be used to get a new `access_token` even after it
 has expired. This is incredibly useful, eg. for applications that wish to
 perform resource access on a schedule.

The EVE SSO implementation of the authorization code flow appends the code as a
 query parameter to the URL so it will be visible to the server side of the
 application without any additional work on the client side.

## Additional Notes

The suggestions made on this page outline the easiest authorization flow to use
 with client and server side applications, as well as some best practice reasoning.
 They are just suggestions and there could be any number of reasons to use the
 authorization code flow in a client  side application, or pass the token acquired
 with the implicit flow back to the application server.
