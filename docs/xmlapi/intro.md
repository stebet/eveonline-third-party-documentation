# Deprecation Notice
This API will be shut down May 8th, 2018 or earlier if metrics signal a trivial level of usage, please use [ESI](../esi/index.md) instead.
The following is kept for historical purposes.

# Introduction
The EVE XML API is an HTTP **read only** API to the EVE Universe. The API has both publicly accessible information and private character/corporation information. Using the API does not require any kind of registration, simply point your HTTP requests to the correct locations, or use one of the many third-party libraries, and away you go.

## Accessing The API
As the XML API is an HTTP API you can access it by simply pointing your browser at the correct endpoints. An example of this would be: `https://api.eveonline.com/eve/CharacterInfo.xml.aspx?characterID={character_id_here}`

The above will take you to the public character information for the specific character ID.

If you would like to access private information you will need to authenticate using one of the available methods as described in [Authentication](authentication.md).

## User-Agent
Consuming the XML API does not require you as a developer to register or pass any unique identification with each request. While this is makes getting into and developing with the API very easy, it means aside from the IP address CCP has very little way in identifying who the requests are coming from.

We ask that if you are going to consume the API that you pass a custom [User-Agent](https://en.wikipedia.org/wiki/User_agent) header along with your requests. The User-Agent should primarily include information on how we can contact you, but it is also a good idea to include your application name and version.

If at all possible if something goes wrong with you application and we are considering banning it from the API, we will attempt to contact you first before banning. There are of course other reasons for us to contact you, but that is the primary one.

A good User-Agent header makes CCP very happy.

## Schema
The returned response of the XML API follows the following schema:
```xml
<eveapi version="2">
    <currentTime>DateTime</currentTime>
    <result>
        Various result schemas
    </result>
    <cachedUntil>DateTime</cachedUntil>
</eveapi>
```
The `DateTime` is always of the format `yyyy-MM-dd HH:mm:ss`.

The result schema can have various combinations like:
```xml
<result>
    <xmlElement>Some text</xmlElement>
    ...
    <xmlElement>
        <xmlElement>Some text</xmlElement>
        ...
    </xmlElement>
</result>
```
or
```xml
<result>
    <xmlElement>Some text</xmlElement>
    ...
</result>
```
or
```xml
<result>
    <rowset name="" key="" columns="">
        <row attributte1="" attributte2="" attributte3="" attributte4=""/>
        ...
    </rowset>
</result>
```
or a combination of all above schemas.

The **Sample Response** in each call page, displays the `result` schema.

## Test Server
The Singularity test server has the XML API running and is in most cases updated before Tranquility. We do highly encourage third-party developers to test new API features on Singularity and provide feedback.

New features being deployed to Singularity will often be announced in the dev blogs of the developer web site and/or the [technology lab](https://forums.eveonline.com/default.aspx?g=topics&f=263) forums section.
