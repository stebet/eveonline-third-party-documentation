# NPC Corporations

The npccorps resource allows an application to read information on the various NPC Corporations.

## NPC Corporations
### Route
``/corporations/npccorps/``


### API version

NPCCorporationsCollection-v1+json

### GET
* Cache: 1 hour

```json
{
  "totalCount_str": "239",
  "items": [
    {
      "description": "The internal corporation used for characters in graveyard.",
      "headquarters": {
        "href": "https://crest-tq.eveonline.com/stations/60000001/",
        "name": ""
      },
      "href": "https://crest-tq.eveonline.com/corporations/1000001/",
      "id_str": "1000001",
      "loyaltyStore": {
        "href": "https://crest-tq.eveonline.com/corporations/1000001/loyaltystore/"
      },
      "ticker": "666",
      "id": 1000001,
      "name": "Doomheim"
    },
    {
      "description": "The CBD Corporation is one of the biggest exporters/importers in Caldari space. The corporation has established trade links far and wide, with a huge amount of goods in constant fluctuation.",
      "headquarters": {
        "href": "https://crest-tq.eveonline.com/stations/60000004/",
        "name": "Muvolailen X - Moon 3 - CBD Corporation Storage"
      },
      "href": "https://crest-tq.eveonline.com/corporations/1000002/",
      "id_str": "1000002",
      "loyaltyStore": {
        "href": "https://crest-tq.eveonline.com/corporations/1000002/loyaltystore/"
      },
      "ticker": "CBDC",
      "id": 1000002,
      "name": "CBD Corporation"
    },
    { "..." },
    { "..." },
    { "..." }
  ],
  "pageCount": 1,
  "pageCount_str": "1",
  "totalCount": 239
}
```
