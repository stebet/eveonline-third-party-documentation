# Introduction
## What is the SSO
Simply put, SSOs are a way for users to log into one web site using their username and password from another web site. For example, if go to [https://www.goodreads.com/](https://www.goodreads.com/) and try to sign in they will ask you if you want to sign in with Facebook, Twitter, Google, or even Amazon. For Goodreads this is great because it means they don't have to worry about trying to manage your username and password information. It also has the nice advantage of making it a lot easier for you as a user to sign into their site as you don't need to register or keep track of multiple extra account names and passwords.

For EVE Online, the SSO means that you can sign into a web site that has integrated the EVE SSO and confirm you are a specific character. While signing into a site you will be asked which character you wish to authenticate with and the web site that let you sign in with the EVE SSO will get confirmation from CCP that you own that character. The original web site will only ever get your character, they never see your account name or password. The original web site will not know what account that character is on or have any way, from us at least, of linking that character to any other character on the same account.

## Registering for the SSO
To use the SSO in your app, you must first register it at [the developers site](https://developers.eveonline.com/). When you create a new application here it will give you a client ID and secret key, which are used in the authentication flow.

You are required to supply the following:
- Name: Name of the application, will be displayed to the users when asked to authorize your app.
- Description: Description of the application, will be listed under your app in [Third Party Applications](https://community.eveonline.com/support/third-party-applications/).
- Connection type: Can be API Access or Authentication Only. If API Access is selected, you will also need to select the scopes your app will use.
- Callback URL: Callback URL, which is the only location the login server will redirect back to after the user has authorized the login (See [Authentication flow](authentication.md) for details.)

### Errors
Please note:

If too many HTTP requests are done to an SSO endpoint within a set time interval the SSO will return a HTTP 409 response (being vague on the number of requests and time on purpose as we will be tuning these values).

### Test Server
All instances of https://login.eveonline.com can be swapped for https://sisilogin.testeveonline.com when trying to use Sisi.

### Login Images
When creating a button to direct users to login to your site or application with the EVE SSO please use one of the following images for the button. This helps create consistency for EVE players and when they view your site or application will more easily be able to quickly identify that it supports the EVE SSO.

![EVE SSO Login Buttons Large White](https://web.ccpgamescdn.com/eveonlineassets/developers/eve-sso-login-white-large.png)

![EVE SSO Login Buttons Large Black](https://web.ccpgamescdn.com/eveonlineassets/developers/eve-sso-login-black-large.png)

![EVE SSO Login Buttons Small White](https://web.ccpgamescdn.com/eveonlineassets/developers/eve-sso-login-white-small.png)

![EVE SSO Login Buttons Small Black](https://web.ccpgamescdn.com/eveonlineassets/developers/eve-sso-login-black-small.png)
