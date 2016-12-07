# Location
The characters location resource allows an application to read a character's location.

### Route
``/characters/<characterID:characterIdType>/location/``

### GET
* Cache: 5 seconds
* Scope: `characterLocationRead`

User has to be online to see his location, if he is offline then the response is empty.

```json
{
  "solarSystem": {
    "id_str": "30002782",
    "href": "https://crest-tq.eveonline.com/solarsystems/30002782/",
    "id": 30002782,
    "name": "Kamio"
  }
}
```
