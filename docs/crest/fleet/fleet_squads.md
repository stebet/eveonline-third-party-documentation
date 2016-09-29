# Fleet Squads

## Fleet Squads

The fleet squads collection allows you to create new squads.

- **Route:** [Fleet](fleet_fleet.md) → `wings.href` → `items[].squads.href`
- **Example URL:** `https://crest-tq.eveonline.com/fleets/1060711261968/wings/2073711261968/squads/`

### POST

- **Scope:** `fleetWrite`

#### Sample Request

**Media type:** `application/vnd.ccp.eve.FleetSquadCreate-v1+json`

```json
{}
```

#### Notes

- No information about the newly created squad will be returned in the response.

## Fleet Squads

The fleet squad resource allows you to delete or rename a squad.

- **Route:** [Fleet](fleet_fleet.md) → `wings.href` → `items[].squadsList[].href`
- **Example URL:** `https://crest-tq.eveonline.com/fleets/1060711261968/wings/2073711261968/squads/3129411261968/`

### DELETE

- **Scope:** `fleetWrite`

#### Sample Request

**Media type:** `application/vnd.ccp.eve.FleetSquadDelete-v1+json`

```json
{}
```

#### Notes

- Only empty squads can be deleted.

### PUT

- **Scope:** `fleetWrite`

#### Sample Request

**Media type:** `application/vnd.ccp.eve.FleetSquadUpdate-v1+json`

```json
{
  "name": "New name"
}
```

#### Request Details

- `name`: New name of the squad. May not be longer than 10 characters.

## References

- [Patch notes](https://community.eveonline.com/news/patch-notes/patch-notes-for-eve-online-citadel) for EVE Online: Citadel
