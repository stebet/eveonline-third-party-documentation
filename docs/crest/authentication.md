# Authentication and Scopes
When designing your application you will need to decide what information you require from CREST and if any of that information requires authentication.

Currently most data does not require authentication. Anything that is not public will have a scope attached. In order to access these endpoints, your app must have been set up with that scope enabled on the dev site and you must have requested that scope when getting your access token from the SSO.

Once you have decided what scopes you require for your app, you will need to follow the instructions in the [SSO section](../sso/intro.md) to register your app on the dev site and then to get an access token.

## Scopes
When designing your application you will need to decide what information you require from CREST and if any of that information requires authentication.

### publicData
The first scope released. Not required by any resources, as public data doesn't require any authentication anymore.

### characterAccountRead
Allows an application to read your character's account information.

### characterAssetsRead
Allows an application to read your character's assets.

### characterBookmarksRead
Allows an application to read your character's bookmarks.

### characterCalendarRead
Allows an application to read your character's calendar.

### characterChatChannelsRead
Allows an application to read a list of the chat channels your character is in.

### characterClonesRead
Allows an application to read a list of your character's clones.

### characterContactsRead
Allows access to reading your character's contacts.

### characterContactsWrite
Allows access to create and update your character's contacts.

### characterFactionalWarfareRead

Allows an application to read your character's FW information.

### characterFittingsRead
Allows an application to read all of the saved fits for a character.

### characterFittingsWrite
Allows an application to create new saved fits as well as delete existing ones.

### characterIndustryJobsRead
Allows an application to read your character's industry jobs.

### characterKillsRead
Allows an application to read your character's killmails. Only killmail that the character is the victim or the finalBlow will be returned with this scope.

### characterLocationRead
Allows an application to read your character's current location.

### characterMailRead
Allows an application to read your character's mail.

### characterMarketOrdersRead
Allows an application to read your character's market orders.

### characterMedalsRead
Allows an application to read your character's medals.

### characterNavigationWrite
Allows an application to set your auto-pilot waypoints on your client.

### characterNotificationsRead
Allows an application to read your character's notifications.

### characterResearchRead
Allows an application to read your character's research information.

### characterSkillsRead
Allows an application to read your character's skills.

### characterWalletRead
Allows an application to read your character's wallet.

## Using your access token
Once you have a valid access token from the SSO, you can make calls to authenticated CREST by adding an Authorization header and using the auth'd crest endpoint.
```http
Authorization: Bearer [Your access token]
```
An authenticated call that lists all regions would look like this (note that the url here should have been obtained dynamically from the root endpoint, rather than being hardcoded):
```http
POST https://crest-tq.eveonline.com/regions/ HTTP/1.1

Authorization: Bearer bG9...ZXQ=
Accept: application/vnd.ccp.eve.RegionCollection-v1+json
Host: crest-tq.eveonline.com
```    
For information on the Accept header used here, see the [Versioning](versioning.md) section.
