# Wars, War, and War Killmails
The wars resource allows an application to read wars data.

## Wars
### Route
``/wars/``

### GET
* Cache: 1 day

```json
{
  "totalCount_str": "477886",
  "pageCount": 239,
  "items": [
    {
      "href": "https://crest-tq.eveonline.com/wars/1/",
      "id": 1,
      "id_str": "1"
    },
    { "..." },
    { "..." },
    { "..." },
    { "..." }
   ],
  "next": {
    "href": "https://crest-tq.eveonline.com/wars/?page=2"
  },
  "totalCount": 477886,
  "pageCount_str": "239"
}
```

## War
### Route
``/wars/<warID:warIdType>/``

### GET
* Cache: 1 hour

```json
{
  "id": 42000,
  "timeFinished": "2007-10-29T14:29:00",
  "openForAllies": false,
  "timeStarted": "2007-10-22T13:36:00",
  "allyCount": 3,
  "timeDeclared": "2007-10-21T13:36:00",
  "aggressor": {
    "shipsKilled": 0,
    "shipsKilled_str": "0",
    "name": "Privateer Alliance",
    "href": "https://crest-tq.eveonline.com/alliances/753644383/",
    "id_str": "753644383",
    "icon": {
      "href": "http://imageserver.eveonline.com/Alliance/753644383_128.png"
    },
    "id": 753644383,
    "iskKilled": 0.0
  },
  "mutual": false,
  "allyCount_str": "3",
  "killmails": "https://crest-tq.eveonline.com/wars/42000/killmails/all/",
  "id_str": "42000",
  "defender": {
    "shipsKilled": 0,
    "shipsKilled_str": "0",
    "name": "Ka-Tet",
    "href": "https://crest-tq.eveonline.com/alliances/389924442/",
    "id_str": "389924442",
    "icon": {
      "href": "http://imageserver.eveonline.com/Alliance/389924442_128.png"
    },
    "id": 389924442,
    "iskKilled": 0.0
  },
  "allies":[  
      {  
         "id_str":"98414924",
         "href":"https://crest-tq.eveonline.com/corporations/98414924/",
         "id":98414924,
         "name":"Mordu's Foreign Legion",
         "icon":{  
            "href":"http://imageserver.eveonline.com/Corporation/98414924_128.png"
         }
      },
      { "..." },
      { "..." }
   ]
  }
```


## War Killmails
### Routes
``/wars/<warID:warIdType>/killmails/all``

### GET
* Cache: 1 hour

```json
{
  "totalCount": 75,
  "totalCount_str": "75",
  "pageCount": 3,
  "pageCount_str": "3",
  "items": [
    {
       "href":"https://crest-tq.eveonline.com/killmails/55818219/53b4a9c6c8119eacafd407977ae7a93033b081c6/",
       "id":55818219,
       "id_str":"55818219"
    },
    { "..." },
    { "..." },
    { "..." },
    { "..." }
   ],
  "next": {
    "href": "https://crest-tq.eveonline.com/wars/505250/killmails/all/?page=2"
  }
}
```
