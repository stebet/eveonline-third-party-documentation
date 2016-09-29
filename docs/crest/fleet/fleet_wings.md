# Fleet Wings

## Fleet Wings

The fleet wings collection provides details about the fleet's wings and squads, and allows you to create new wings.

- **Route:** [Fleet](fleet_fleet.md) → `wings.href`
- **Example URL:** `https://crest-tq.eveonline.com/fleets/1060711261968/wings/`

### GET

- **Cache:** 5 seconds
- **Scope:** `fleetRead`

#### Sample Response

**Media type:** `application/vnd.ccp.eve.FleetWings-v1+json`

```json
{
  "totalCount_str": "1",
  "items": [
    {
      "name": "Wing 1",
      "href": "https://crest-tq.eveonline.com/fleets/1060711261968/wings/2073711261968/",
      "squadsList": [
        {
          "id_str": "3129411261968",
          "href": "https://crest-tq.eveonline.com/fleets/1060711261968/wings/2073711261968/squads/3129411261968/",
          "id": 3129411261968,
          "name": "Squad 1"
        }
      ],
      "id_str": "2073711261968",
      "squads": {
        "href": "https://crest-tq.eveonline.com/fleets/1060711261968/wings/2073711261968/squads/"
      },
      "id": 2073711261968
    }
  ],
  "pageCount": 1,
  "pageCount_str": "1",
  "totalCount": 1
}
```

#### Response Details

- `name`: Name of the wing.
- `href`: URL of the wing resource.
- `squadsList`: List containing details of the wing's squads.
- `squads`: Contains link to the wing's squad collection.
- `id`: ID of the wing.

#### Notes

- All items will be listed on a single page.

### POST

- **Scope:** `fleetWrite`

#### Sample Request

**Media type:** `application/vnd.ccp.eve.FleetWingCreate-v1+json`

```json
{}
```

#### Notes

- No information about the newly created wing will be returned in the response.

## Fleet Wing

The fleet wing resource allows you to delete or rename a wing.

- **Route:** [Fleet](fleet_fleet.md) → `wings.href` → `items[].href`
- **Example URL:** `https://crest-tq.eveonline.com/fleets/1060711261968/wings/2073711261968/`

### DELETE

- **Scope:** `fleetWrite`

#### Sample Request

**Media type:** `application/vnd.ccp.eve.FleetWingDelete-v1+json`

```json
{}
```

#### Notes

- Only empty wings can be deleted. The wing may contain squads, but the squads must be empty.

### PUT

- **Scope:** `fleetWrite`

#### Sample Request

**Media type:** `application/vnd.ccp.eve.FleetWingUpdate-v1+json`

```json
{
  "name": "New name"
}
```

#### Request Details

- `name`: New name of the wing. May not be longer than 10 characters.

## References

- [Patch notes](https://community.eveonline.com/news/patch-notes/patch-notes-for-eve-online-citadel) for EVE Online: Citadel
