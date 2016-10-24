# Static Data Export

- [Introduction](intro.md)
- [Conversions](conversions.md)
- [Tips](tips.md)

## Included Files

### Microsoft SQL Server Dump File

The SDE includes a Microsoft SQLServer dump file with several reference tables.
Originally, almost all reference data was included in the SQLServer dump.
The [EVE Development Network](http://wiki.eve-id.net/Category:CCP_DB_Tables) documents
much of the original contents of the dump file.

The current SQLServer dump contains the following tables:

- [Agents Table](mssql/mssql_agtAgents.md)
- [Research Agents Table](mssql/mssql_agtResearchAgents.md)
- [Factions Table](mssql/mssql_chrFactions.md)
- [NPC Corporations Table](mssql/mssql_crpNPCCorporations.md)
- [EVE Units Table](mssql/mssql_eveUnits.md)
- [Inventory Flags Table](mssql/mssql_invFlags.md)
- [Inventory Items Table](mssql/mssql_invItems.md)
- [Inventory Meta Types Table](mssql/mssql_invMetaTypes.md)
- [Inventory Names Table](mssql/mssql_invNames.md)
- [Inventory Positions Table](mssql/mssql_invPositions.md)
- [Inventory Type Materials Table](mssql/mssql_invTypeMaterials.md)
- [Inventory Type Reactions Table](mssql/mssql_invTypeReactions.md)
- [Inventory Unique Names Table](mssql/mssql_invUniqueNames.md)
- [Industry Activities Table](mssql/mssql_ramActivities.md)
- [Planet Schematics Table](mssql/mssql_planetSchematics.md)
- [Station Operations Table](mssql/mssql_staOperations.md)
- [Stations Table](mssql/mssql_staStations.md)
- [Station Types Table](mssql/mssql_staStationTypes.md)

### SQLite Database File

The SDE includes an SQLite database file which contains the following tables:

- [Constellations Table](sqlite/sqlite_mapConstellations.md)
- [Denormalize Table](sqlite/sqlite_mapDenormalize.md)
- [Regions Table](sqlite/sqlite_mapRegions.md)
- [Solar Systems Table](sqlite/sqlite_mapSolarSystems.md)

### YAML Files

The SDE includes the following files (in file name order) exported in YAML format:

- [Blueprints (blueprints.yaml)](yaml/yaml_blueprints.md)
- [Certificates (certificates.yaml)](yaml/yaml_certificates.md) 
- [EVE Graphics (graphicIDs.yaml)](yaml/yaml_graphicIDs.md)
- [Groups (groupIDs.yaml)](yaml/yaml_groupIDs.md)
- [EVE Icons (iconIDs.yaml)](yaml/yaml_iconIDs.md)
- [Ship Skins (skins.yaml)](yaml/yaml_skins.md)
- [Skin Licenses (skinLicenses.yaml)](yaml/yaml_skinLicenses.md)
- [Skin Materials (skinMaterials.yaml)](yaml/yaml_skinMaterials.md)
- [Tournament Rules (tournamentRuleSets.yaml)](yaml/yaml_tournamentRuleSets.md)
- [Inventory Types (typeIDs.yaml)](yaml/yaml_typeIDs.md)
