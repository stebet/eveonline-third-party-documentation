# Authentication
There are two methods of authentication available for use with the XML API. As the XML API is a read-only API and only supports GET requests, both involve adding parameters to the query string.

## API keys
API keys are the primary method of accessing private XML API endpoints. They may be created, updated and deleted by users at the [API Key Management](https://community.eveonline.com/support/api-key/) page.

### Usage
To authenticate using an API key, include the key ID and verification code as parameters in the URL.

<table border="1">
  <tbody>
    <tr>
      <th>Parameter</th>
      <th>Value</th>
    </tr>
    <tr>
      <td>keyID</td>
      <td>Key ID of the API key.</td>
    </tr>
    <tr>
      <td>vCode</td>
      <td>Verification code of the API key.</td>
    </tr>
  </tbody>
</table>

Example: `https://api.eveonline.com/account/AccountStatus.xml.aspx?keyID=5342860&vCode=1JlLzA5N7fsKh0keyYfFQtkCfm4VvnO4coFXXUDun2ySQjd66AxxJF0OxljvdwdZ`

### API key parameters
- Name: Name of the API key. Does not have to be unique, and is only visible to the owner of the API key. Irrelevant to end users of the API key, but may make API key management easier for their owners.
- Key ID: Unique ID of the API key. May not be changed.
- Verification code: Alphanumeric string consisting of up to 64 characters. By default, a random full length code will be generated, but the owner may use a verification code of any length. Matches the regular expression `[a-zA-Z0-9]{1,64}`
- Access mask: Bitmask defining which endpoints the API key will provide access to.
- Type: Two main types of API keys are character and corporation keys. Character keys can be further divided into character keys, which provide access to only one chracter, and account keys, which provide access to all characters on an account. Only directors of a corporation may create corporation API keys.
- Expiry date: How long the API key will be valid. By default, API keys are valid for 1 year from the date of creation, but that date may be changed and they may also be set to never expire. Expired API keys may be reactivated by changing the expiry date.

Provided you have the key ID and verification code of an API key, you can use the [/account/APIKeyInfo.xml.aspx](account/account_apikeyinfo.md) endpoint to retrieve most information about it. As all properties of an API key except the key ID may be modified by the owner at any time, it is good practive to use this endpoint for monitoring stored API keys.

### Create predefined API keys
It is possible to ease the process of requesting a specific API key from someone by providing them with a CreatePredefined link. It will take them to the API key creation page, but some or all of the fields may be predefined by the link.

The base URL is `https://community.eveonline.com/support/api-key/CreatePredefined`, and presets are defined by adding a query string to that URL. The parameters which may be used are:

- accessMask: The access mask which the API key should have.
- ownerType: Type of the API key which should be created. Whether a character key is account wide or not is determined by another property. Can be `Character` or `Corporation`, defaults to `Character`.
- ownerID: ID of the character or corporation which the API key applies to. Defaults to 0, which will create an account key instead of a character key.

For example, to request an account wide API key which gives you access to mail of all characters on that account, you can provide your users with the following link: `https://community.eveonline.com/support/api-key/CreatePredefined?accessMask=3584`

## SSO access tokens
SSO access tokens are another method for accessing private endpoints. Compared to API keys, they are more limited as they can't be used for account access. Aside from that limitation, using this method will make things easier for your users as they won't have to bother with creating an API key and giving you the details: they just have to authorize your SSO app.

### Usage
To authenticate using an SSO access token, include the access token as a parameter in the URL. As an access token may contain scopes for both character and corporation access, you must also define which one you will be using.

<table border="1">
  <tbody>
    <tr>
      <th>Parameter</th>
      <th>Value</th>
    </tr>
    <tr>
      <td>accessToken</td>
      <td>SSO access token.</td>
    </tr>
    <tr>
      <td>accessType</td>
      <td>Should be set to <code>character</code> or <code>corporation</code>, depending on which type of access is required. Optional, defaults to <code>character</code>.</td>
    </tr>
  </tbody>
</table>

Example: `https://api.eveonline.com/char/AccountBalance.xml.aspx?characterID=93265215&accessToken=Ls-vx-xMqq03cl7yMPWdWTVyp1TQUod7WyXti_EmuEVaUMt5JQibftknW06mtFDfhLS7khMP7S93QxXeUzGnxw2`

## Access mask reference

### Scope to access mask mappings
These tables list the SSO scopes which allow access to the XML API and the access masks they map to. To check which access mask an access token provides, you may also make a call to the [/account/APIKeyInfo.xml.aspx](account/account_apikeyinfo.md) endpoint using the token.

#### Character access
<table border="1">
  <tbody>
    <tr>
      <th>SSO scope</th>
      <th>Access mask</th>
    </tr>
    <tr><td>characterWalletRead</td><td>1 | 2097152 | 4194304</td></tr>
    <tr><td>characterAssetsRead</td><td>2 | 134217728</td></tr>
    <tr><td>characterCalendarRead</td><td>4 | 1048576</td></tr>
    <tr><td>characterContactsRead</td><td>16 | 32 | 524288</td></tr>
    <tr><td>characterFactionalWarfareRead</td><td>64</td></tr>
    <tr><td>characterIndustryJobsRead</td><td>128</td></tr>
    <tr><td>characterKillsRead</td><td>256</td></tr>
    <tr><td>characterMailRead</td><td>512 | 1024 | 2048</td></tr>
    <tr><td>characterMarketOrdersRead</td><td>4096</td></tr>
    <tr><td>characterMedalsRead</td><td>8192</td></tr>
    <tr><td>characterNotificationsRead</td><td>16384 | 32768</td></tr>
    <tr><td>characterResearchRead</td><td>65536</td></tr>
    <tr><td>characterSkillsRead</td><td>131072 | 262144 | 1073741824</td></tr>
    <tr><td>characterAccountRead</td><td>33554432</td></tr>
    <tr><td>characterContractsRead</td><td>67108864</td></tr>
    <tr><td>characterBookmarksRead</td><td>268435456</td></tr>
    <tr><td>characterChatChannelsRead</td><td>536870912</td></tr>
    <tr><td>characterClonesRead</td><td>2147483648</td></tr>
  </tbody>
</table>

#### Corporation access
<table border="1">
  <tbody>
    <tr>
      <th>SSO scope</th>
      <th>Access mask</th>
    </tr>
    <tr><td>corporationWalletRead</td><td>1 | 8 | 1048576 | 2097152</td></tr>
    <tr><td>corporationAssetsRead</td><td>2 | 32 | 16777216</td></tr>
    <tr><td>corporationMedalsRead</td><td>4 | 8192</td></tr>
    <tr><td>corporationContactsRead</td><td>16 | 262144</td></tr>
    <tr><td>corporationFactionalWarfareRead</td><td>64</td></tr>
    <tr><td>corporationIndustryJobsRead</td><td>128</td></tr>
    <tr><td>corporationKillsRead</td><td>256</td></tr>
    <tr><td>corporationMembersRead</td><td>512 | 1024 | 2048 | 4194304 | 33554432</td></tr>
    <tr><td>corporationMarketOrdersRead</td><td>4096</td></tr>
    <tr><td>corporationStructuresRead</td><td>16384 | 32768 | 131072 | 524288</td></tr>
    <tr><td>corporationShareholdersRead</td><td>65536</td></tr>
    <tr><td>corporationContractsRead</td><td>8388608</td></tr>
    <tr><td>corporationBookmarksRead</td><td>67108864</td></tr>
  </tbody>
</table>
