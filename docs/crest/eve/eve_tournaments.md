# Alliance Tournaments
These resources allows an application to read tournaments with associated series, matches, and teams.

## Tournaments
### Route
``/tournaments/``

### API version

TournamentCollection-v1+json

### GET
* Cache: 5 minutes

```json
{
  "totalCount_str":"14",
  "items":[
    {
      "href":{
        "href":"https://crest-tq.eveonline.com/tournaments/1/",
        "name":"Alliance Tournament XI"
      }
    },
    { "..."},
    { "..."},
    { "..."},
    {
      "href":{
        "href":"https://crest-tq.eveonline.com/tournaments/14/",
        "name":"Amarr Championships Round Robin"
      }
    }
  ],
  "pageCount":1,
  "pageCount_str":"1",
  "totalCount":14
}
```

## Tournament
### Route
``/tournaments/<tournamentID:tournamentIdType>/``

### API version

Tournament-v1+json

### GET
* Cache: ()

```json
{
  "series":{
    "href":"https://crest-tq.eveonline.com/tournaments/14/series/"
  },
  "type":"round-robin",
  "name":"Amarr Championships Round Robin",
  "entries":[
    {
      "teamStats":{
        "href":"https://crest-tq.eveonline.com/tournaments/14/teams/224/"
      },
      "href":"https://crest-tq.eveonline.com/tournaments/teams/224/",
      "name":"Ithica Hawk"
    },
    { "..." },
    { "..." },
    { "..." }
  ]
}
```

## Series
### Route
``/tournaments/<tournamentID:tournamentIdType>/series/``

### API version

TournamentSeriesCollection-v1+json

### GET
* Cache: 5 minutes

```json
{
  "totalCount_str":"1",
  "items":[
    {
      "redTeam":{
        "team":{
          "href":"https://crest-tq.eveonline.com/tournaments/teams/197/",
          "teamName":"Barghest flagship"
        },
        "isDecided":true,
        "isBye":false
      },
      "matchesWon":{
        "blueTeam_str":"5",
        "redTeam":3,
        "redTeam_str":"3",
        "blueTeam":5
      },
      "matches":{
        "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/matches/"
      },
      "self":{
        "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/"
      },
      "winner":{
        "isDecided":false,
        "isBye":false
      },
      "loser":{
        "isDecided":false,
        "isBye":false
      },
      "length":10000,
      "length_str":"10000",
      "blueTeam":{
        "team":{
          "href":"https://crest-tq.eveonline.com/tournaments/teams/198/",
          "teamName":"Baalgorn flagship"
        },
        "isDecided":true,
        "isBye":false
      },
      "structure":{

      }
    }
  ],
  "pageCount":1,
  "pageCount_str":"1",
  "totalCount":1
}
```
* Not all Series have all json members, the `isBye` boolean determines if `blueTeam` or `redTeam` `"team"` data is present
```json
{
  "totalCount_str":"27",
  "items":[
    { "..." },
    { "..." },
    {
      "redTeam":{
        "isDecided":true,
        "isBye":true
      },
      "matchesWon":{
        "blueTeam_str":"0",
        "redTeam":0,
        "redTeam_str":"0",
        "blueTeam":0
      },
      "matches":{
        "href":"https://crest-tq.eveonline.com/tournaments/14/series/24/matches/"
      },
      "self":{
        "href":"https://crest-tq.eveonline.com/tournaments/14/series/24/"
      },
      "winner":{
        "team":{
          "href":"https://crest-tq.eveonline.com/tournaments/teams/226/",
          "teamName":"Lysus"
        },
        "isDecided":true,
        "isBye":false
      },
      "loser":{
        "isDecided":true,
        "isBye":true
      },
      "length":1,
      "length_str":"1",
      "blueTeam":{
        "team":{
          "href":"https://crest-tq.eveonline.com/tournaments/teams/226/",
          "teamName":"Lysus"
        },
        "isDecided":true,
        "isBye":false
      },
      "structure":{

      }
    },
    { "..." },
    { "..." },
    { "..." }
  ],
  "pageCount":1,
  "pageCount_str":"1",
  "totalCount":27
}
```

## Teams
### Route
``/tournaments/teams/<teamID:teamIdType>/``

### API version

TournamentTeam-v1+json


### GET
* Cache: ()

```json
{
  "captain":{
    "href":"https://crest-tq.eveonline.com/characters/95465499/",
    "name":"CCP Bartender",
    "icon":{
      "href":"http://imageserver.eveonline.com/Character/95465499_128.jpg"
    }
  },
  "name":"Barghest flagship",
  "iskKilled":1631914,
  "iskKilled_str":"1631914",
  "shipsKilled_str":"3",
  "banFrequency":[

  ],
  "members":{
    "href":"https://crest-tq.eveonline.com/tournaments/teams/197/members/"
  },
  "pilots":[
    {
      "href":"https://crest-tq.eveonline.com/characters/94532560/",
      "name":"CCP Puck",
      "icon":{
        "href":"http://imageserver.eveonline.com/Character/94532560_128.jpg"
      }
    },
    {
      "href":"https://crest-tq.eveonline.com/characters/95465499/",
      "name":"CCP Bartender",
      "icon":{
        "href":"http://imageserver.eveonline.com/Character/95465499_128.jpg"
      }
    },
    {
      "href":"https://crest-tq.eveonline.com/characters/94301268/",
      "name":"CCP Used Ship Saleswoman",
      "icon":{
        "href":"http://imageserver.eveonline.com/Character/94301268_128.jpg"
      }
    },
    {
      "href":"https://crest-tq.eveonline.com/characters/95995047/",
      "name":"Artsan Amruros",
      "icon":{
        "href":"http://imageserver.eveonline.com/Character/95995047_128.jpg"
      }
    }
  ],
  "banFrequencyAgainst":[
    {
      "numBans":1,
      "shipType":{
        "href":"https://crest-tq.eveonline.com/inventory/types/24692/",
        "name":"Abaddon",
        "icon":{
          "href":"http://imageserver.eveonline.com/Type/24692_64.png"
        }
      },
      "numBans_str":"1"
    }
  ],
  "shipsKilled":3
}
```

## TeamStats
### Route
``/tournaments/<tournamentID:tournamentIdType>/teams/<teamID:teamIdType>/``

### API version

TournamentTeam-v1+json

### GET
* Cache: ()

* This endpoint is only accessible via `href` member from the `/tournaments/` endpoint -> "entries" json member, while the above endpoint for `/teams/` is accessible via `/series/`
* The two endpoints provide the same data, except this also has `/matches/` references

```json
{
  "seed_str":"0",
  "banFrequencyAgainst":[
    {
      "numBans":1,
      "shipType":{
        "href":"https://crest-tq.eveonline.com/inventory/types/24692/",
        "name":"Abaddon",
        "icon":{
          "href":"http://imageserver.eveonline.com/Type/24692_64.png"
        }
      },
      "numBans_str":"1"
    }
  ],
  "shipsKilled":3,
  "pilots":[
    {
      "href":"https://crest-tq.eveonline.com/characters/94532560/",
      "name":"CCP Puck",
      "icon":{
        "href":"http://imageserver.eveonline.com/Character/94532560_128.jpg"
      }
    },
    { "..." },
    { "..." },
    { "..." }
  ],
  "matches":[
    {
      "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/matches/0/"
    },
    { "..."},
    { "..."},
    { "..."},
    {
      "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/matches/7/"
    }
  ],
  "iskKilled_str":"1631914",
  "flagshipType":{
    "href":"https://crest-tq.eveonline.com/inventory/types/33820/",
    "name":"Barghest",
    "icon":{
      "href":"http://imageserver.eveonline.com/Type/33820_64.png"
    }
  },
  "shipsKilled_str":"3",
  "name":"Barghest flagship",
  "seed":0,
  "banFrequency":[

  ],
  "members":{
    "href":"https://crest-tq.eveonline.com/tournaments/teams/197/members/"
  },
  "captain":{
    "href":"https://crest-tq.eveonline.com/characters/95465499/",
    "name":"CCP Bartender",
    "icon":{
      "href":"http://imageserver.eveonline.com/Character/95465499_128.jpg"
    }
  },
  "iskKilled":1631914
}
```

## Members
### Route
``/tournaments/teams/<teamID:teamIdType>/members/``

### API version

TournamentTeamMemberCollection-v1+json

### GET
* Cache: ()
* This information is available under the "pilots" json member accessed via either of the above `/teams/` endpoints as well

```json
{
  "totalCount_str":"1",
  "items":[
    {
      "self":{
        "href":"https://crest-tq.eveonline.com/tournaments/teams/197/members/95465499/"
      },
      "character":{
        "href":"https://crest-tq.eveonline.com/characters/95465499/"
      },
      "name":"CCP Bartender",
      "icon":{
        "href":"http://imageserver.eveonline.com/Character/95465499_128.jpg"
      }
    }
  ],
  "pageCount":1,
  "pageCount_str":"1",
  "totalCount":1
}
```


## Matches
### Route
``/tournaments/<tournamentID:tournamentIdType>/series/<seriesID:seriesIdType>/matches/``

### API version

TournamentMatchCollection-v1+json

### GET
* Cache: ()

```json
{
  "totalCount_str":"8",
  "items":[
    {
      "winner":{
        "href":"https://crest-tq.eveonline.com/tournaments/teams/197/"
      },
      "stats":{
        "pilots":{
          "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/matches/0/pilotstats/"
        }
      },
      "redTeam":{
        "href":"https://crest-tq.eveonline.com/tournaments/teams/197/",
        "teamName":"Barghest flagship"
      },
      "bans":{
        "self":{
          "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/matches/0/bans/"
        },
        "redTeam":[
          {
            "typeBans":[

            ],
            "bannedBy":{
              "href":"https://crest-tq.eveonline.com/tournaments/teams/197/"
            }
          }
        ],
        "blueTeam":[
          {
            "typeBans":[

            ],
            "bannedBy":{
              "href":"https://crest-tq.eveonline.com/tournaments/teams/198/"
            }
          }
        ]
      },
      "finalized":true,
      "series":{
        "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/"
      },
      "tournament":{
        "href":"https://crest-tq.eveonline.com/tournaments/7/"
      },
      "score":{
        "redTeam":100.0,
        "blueTeam":98.0
      },
      "blueTeam":{
        "href":"https://crest-tq.eveonline.com/tournaments/teams/198/",
        "teamName":"Baalgorn flagship"
      },
      "inProgress":false
    },
    { "..." },
    { "..." },
    { "..." }
  ],
  "pageCount":1,
  "pageCount_str":"1",
  "totalCount":8
}
```


## Match
### Route
``/tournaments/<tournamentID:tournamentIdType>/series/<seriesID:seriesIdType>/matches/<matchesID:matchesIdType>/``

### API version

TournamentMatch-v1+json

### GET
* Cache: ()
* This data is identical to that obtained in the `/matches/` endpoint above
```json
{
  "winner":{
    "href":"https://crest-tq.eveonline.com/tournaments/teams/197/"
  },
  "stats":{
    "pilots":{
      "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/matches/0/pilotstats/"
    }
  },
  "redTeam":{
    "href":"https://crest-tq.eveonline.com/tournaments/teams/197/",
    "teamName":"Barghest flagship"
  },
  "bans":{
    "self":{
      "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/matches/0/bans/"
    },
    "redTeam":[
      {
        "typeBans":[

        ],
        "bannedBy":{
          "href":"https://crest-tq.eveonline.com/tournaments/teams/197/"
        }
      }
    ],
    "blueTeam":[
      {
        "typeBans":[

        ],
        "bannedBy":{
          "href":"https://crest-tq.eveonline.com/tournaments/teams/198/"
        }
      }
    ]
  },
  "finalized":true,
  "series":{
    "href":"https://crest-tq.eveonline.com/tournaments/7/series/0/"
  },
  "tournament":{
    "href":"https://crest-tq.eveonline.com/tournaments/7/"
  },
  "score":{
    "redTeam":100.0,
    "blueTeam":98.0
  },
  "blueTeam":{
    "href":"https://crest-tq.eveonline.com/tournaments/teams/198/",
    "teamName":"Baalgorn flagship"
  },
  "inProgress":false
}
```


## Bans
### Route
``/tournaments/<tournamentID:tournamentIdType>/series/<seriesID:seriesIdType>/bans/``

### API version

TournamentTypeBanCollection-v1+json

### GET
* Cache: ()
* This is identical to the two separate team bans with the associated `/series/`

```json
{
  "totalCount_str":"2",
  "items":[
    {
      "typeBans":[

      ],
      "bannedBy":{
        "href":"https://crest-tq.eveonline.com/tournaments/teams/197/"
      }
    },
    {
      "typeBans":[

      ],
      "bannedBy":{
        "href":"https://crest-tq.eveonline.com/tournaments/teams/198/"
      }
    }
  ],
  "pageCount":1,
  "pageCount_str":"1",
  "totalCount":2
}
```


## PilotStats
### Route
``/tournaments/<tournamentID:tournamentIdType>/series/<seriesID:seriesIdType>/matches/<matchesID:matchesIdType>/pilotstats/``

### API version

TournamentPilotStatsCollection-v1+json

### GET
* Cache: ()

```json
{
  "totalCount_str":"2",
  "items":[
    {
      "damageDone":1608.52761071,
      "damageReceived":0.0,
      "pilotTournamentStats":{
        "href":"https://crest-tq.eveonline.com/tournaments/7/pilots/94532560/"
      },
      "isDead":false,
      "shipType":{
        "href":"https://crest-tq.eveonline.com/inventory/types/603/",
        "name":"Merlin",
        "icon":{
          "href":"http://imageserver.eveonline.com/Type/603_64.png"
        }
      },
      "team":{
        "href":"https://crest-tq.eveonline.com/tournaments/teams/197/"
      },
      "pilot":{
        "href":"https://crest-tq.eveonline.com/characters/94532560/",
        "name":"CCP Puck",
        "icon":{
          "href":"http://imageserver.eveonline.com/Character/94532560_128.jpg"
        }
      }
    },
    { "..." }
  ],
  "pageCount":1,
  "pageCount_str":"1",
  "totalCount":2
}
```
