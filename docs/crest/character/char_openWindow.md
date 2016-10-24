# Open Window
The open window resource allows an application to open various windows inside the client.

## Open Market Details
The characters openWindow marketdetails resource allows an application to open the market details window for a specific typeID inside the client.

### Route
``/characters/<characterID:characterIdType>/ui/openwindow/marketdetails/``

### POST
* Scope: `remoteClientUI`

The typeID in the href of body does not matter and can remain 0.  However it may be good practice to include the typeID in the href url as a means of future poofing.

User has to be online for window to open, response is empty if offline.

Body format:

```json
{
    "type":     {
      "href": "https://crest-tq.eveonline.com/inventory/types/34/",
      "id": 34
    }
}
```

There is no response, if the action is successful the market details window will open.

## Open Contract
The characters openwindow contract resource allows an application to open a specific contract inside the client.

### Route
``/characters/<characterID:characterIdType>/ui/openwindow/contract/``

### POST
* Scope: `remoteClientUI`

User has to be online for window to open, response is empty if offline.

Body format:

```json
{
	"contractID": 106338363
}
```

There is no response, if the action is successful the contract will open.

## Open Owner Details
The characters openWindow ownerdetails resource allows an application to open an info window about the requested character, corporation, or alliance inside the client.

### Route
``/characters/<characterID:characterIdType>/ui/openwindow/ownerdetails/``

### POST
* Scope: `remoteClientUI`

User has to be online for window to open, response is empty if offline.

Body format:

```json
{

      "id": 99002938
}
```

There is no response, if the action is successful the info window will open.

### Route
``/characters/<characterID:characterIdType>/ui/openwindow/newmail/``

### POST
* Scope: `remoteClientUI`

User has to be online for window to open, response is empty if offline.

Body format:

```json
{

      "subject": "Hello",
      "body": "I would like to negotiate BPO prices with you.",
      "recipients": [{"id": 1536904870}]
}
```

There is no response, if the action is successful the mail window will open.  The body parameter accepts Eve's basic HTML markdown formatting.  Multiple recipients can be present in the array in the above object formatting.