# Station

The stations resource allows an application to read station information.

## Station
### Route
``/stations/<stationID:stationIdType>/``


### API version

Station-v1+json

### GET
* Cache: 5 minutes
* example from above response: [https://crest-tq.eveonline.com/stations/60000004/](https://crest-tq.eveonline.com/stations/60000004/)

```json
{
  "reprocessingEfficiency": 0.5,
  "officeRentalCost": 599539,
  "maxShipVolumeDockable": 50000000,
  "reprocessingStationsTake": 0.05,
  "system": {
    "href": "https://crest-tq.eveonline.com/solarsystems/30002780/",
    "name": "Muvolailen"
  },
  "services": [
    {
      "serviceName": "repair-facilities"
    },
    {
      "serviceName": "courier-missions"
    },
    {
      "serviceName": "reprocessing-plant"
    },
    {
      "serviceName": "office-rental"
    },
    {
      "serviceName": "loyalty-point-store"
    },
    {
      "serviceName": "storage"
    },
    {
      "serviceName": "news"
    },
    {
      "serviceName": "navy-offices"
    },
    {
      "serviceName": "insurance"
    },
    {
      "serviceName": "market"
    },
    {
      "serviceName": "docking"
    },
    {
      "serviceName": "fitting"
    }
  ],
  "race": {
    "href": "https://crest-tq.eveonline.com/races/1/",
    "id": 1,
    "id_str": "1"
  },
  "owner": {
    "href": "https://crest-tq.eveonline.com/corporations/1000002/"
  },
  "position": {
    "y": 256414064640,
    "x": 1723680890880,
    "z": -60755435520
  },
  "type": {
    "href": "https://crest-tq.eveonline.com/inventory/types/1531/"
  },
  "name": "Muvolailen X - Moon 3 - CBD Corporation Storage"
}
```
