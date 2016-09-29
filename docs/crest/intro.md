# Introduction
CREST is the new RESTfull API, destined to replace the older XML API. Currently there is far less data available on CREST, so the XML API is not going away for a long time. The main selling points of CREST include:

* CREST is capable of allowing write access, as well as read.
* CREST communicates directly with the game servers, rather than the backend database, so can better reflect the current state of the game.
* CREST is built with high traffic and complex loads in mind and has strong caching. Expect shorter cache timers and better performance and reliability.

## Walking
CREST is designed to be a properly RESTful API with good support for versioning and changes. As such, a well designed app will not break when things are changed on the API (most of the time!). To enable this one of the things your app should do is generate links to endpoints dynamically. The only hard coded URL will be to the root resource. Here you will find a list of all the other top level endpoints, with href elements for each.

* To get the base list of endpoints, you simply need to make an HTTP GET request to the appropriate root (SISI or TQ).
* To dynamically acquire possible authed endpoints, you should make an authed HTTP GET request to the `decode` endpoint.

For more details on walking through endpoints, see the appropriate section of these docs.
