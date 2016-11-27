# Clones
Retrieve clones and basic attributes portion of character sheet.

* __Path:__ ``/char/Clones.xml.aspx``
* __Cache timer:__ 1 hour
* __Access mask:__ 2147483648 or 8
* __Parameters:__
    <table border="1">
        <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
            <tr>
                <td>characterID</td>
                <td><strong>long</strong></td>
                <td>Character ID for which clones and attributes  will be requested</td>
            </tr>
        </tbody>
    </table>

### Sample Response

```xml
<result>
    <DoB>2010-05-16 03:38:00</DoB>
    <race>Caldari</race>
    <bloodLineID>1</bloodLineID>
    <bloodLine>Deteis</bloodLine>
    <ancestryID>12</ancestryID>
    <ancestry>Tube Child</ancestry>
    <gender>Male</gender>
    <freeRespecs>3</freeRespecs>
    <cloneJumpDate>0001-01-01 00:00:00</cloneJumpDate>
    <lastRespecDate>0001-01-01 00:00:00</lastRespecDate>
    <lastTimedRespec>0001-01-01 00:00:00</lastTimedRespec>
    <remoteStationDate>0001-01-01 00:00:00</remoteStationDate>
    <attributes>
        <intelligence>20</intelligence>
        <memory>20</memory>
        <charisma>19</charisma>
        <perception>20</perception>
        <willpower>20</willpower>
    </attributes>
    <rowset name="implants" key="typeID" columns="typeID,typeName">
        <row typeID="10225" typeName="Social Adaptation Chip - Standard"/>
        <row typeID="10216" typeName="Ocular Filter - Standard"/>
        <row typeID="10212" typeName="Neural Boost - Standard"/>
        <row typeID="10208" typeName="Memory Augmentation - Standard"/>
        <row typeID="10221" typeName="Cybernetic Subprocessor - Standard"/>
    </rowset>
    <rowset name="jumpClones" key="jumpCloneID" columns="jumpCloneID,typeID,locationID,cloneName"/>
    <rowset name="jumpCloneImplants" key="jumpCloneID" columns="jumpCloneID,typeID,typeName"/>
    <jumpActivation>0001-01-01 00:00:00</jumpActivation>
    <jumpFatigue>0001-01-01 00:00:00</jumpFatigue>
    <jumpLastUpdate>0001-01-01 00:00:00</jumpLastUpdate>
</result>
```

### Result Data

<table border="1">
    <tbody>
        <tr>
            <td>DoB</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Date character was created.</td>
        </tr>
        <tr>
            <td>race</td>
            <td><strong>string</strong></td>
            <td></td>
            <td>Characters race.</td>
        </tr>
        <tr>
            <td>bloodLineID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_chrBloodlines.html">[1]</a>
                </sup>
            </td>
            <td></td>
            <td>ID for character bloodline.</td>
        </tr>
        <tr>
            <td>bloodLine</td>
            <td><strong>string</strong></td>
            <td></td>
            <td>Character bloodline.</td>
        </tr>
        <tr>
            <td>ancestryID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_chrAncestries.html">[1]</a>
                </sup>
            </td>
            <td></td>
            <td>ID for character ancestry.</td>
        </tr>
        <tr>
            <td>ancestry</td>
            <td><strong>string</strong></td>
            <td></td>
            <td>Character ancestry.</td>
        </tr>
        <tr>
            <td>gender</td>
            <td><strong>string</strong></td>
            <td></td>
            <td>Character gender.</td>
        </tr>
        <tr>
            <td>freeRespecs</td>
            <td><strong>int</strong></td>
            <td></td>
            <td>Number of available character attribute respecs.</td>
        </tr>
        <tr>
            <td>cloneJumpDate</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Last character clone jump.</td>
        </tr>
        <tr>
            <td>lastRespecDate</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Last character attribute respec.</td>
        </tr>
        <tr>
            <td>lastTimedRespec</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Last character attribute respec. (Using respec accrued over time (1 year))</td>
        </tr>
        <tr>
            <td>remoteStationDate</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Last remote change of home station.</td>
        </tr>
        <tr>
            <td>attributes</td>
            <td><strong>object</strong></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td>intelligence</td>
            <td><strong>int</strong></td>
            <td>Intelligence attribute.</td>
        </tr>
        <tr>
            <td></td>
            <td>memory</td>
            <td><strong>int</strong></td>
            <td>Memory attribute.</td>
        </tr>
        <tr>
            <td></td>
            <td>charisma</td>
            <td><strong>int</strong></td>
            <td>Charisma attribute.</td>
        </tr>
        <tr>
            <td></td>
            <td>perception</td>
            <td><strong>int</strong></td>
            <td>Perception attribute.</td>
        </tr>
        <tr>
            <td></td>
            <td>willpower</td>
            <td><strong>int</strong></td>
            <td>Willpower attribute.</td>
        </tr>
        <tr>
            <td>implants</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing one row per implant.</td>
        </tr>
        <tr>
            <td></td>
            <td>typeID</td>
            <td><strong>int</strong></td>
            <td>Type ID of the implant.</td>
        </tr>
        <tr>
            <td></td>
            <td>typeName</td>
            <td><strong>string</strong></td>
            <td>Name of the implant.</td>
        </tr>
        <tr>
            <td>jumpClones</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing one row per jump clone.</td>
        </tr>
        <tr>
            <td></td>
            <td>jumpCloneID</td>
            <td><strong>int</strong></td>
            <td>Unique jump clone identifier.</td>
        </tr>
        <tr>
            <td></td>
            <td>cloneTypeID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/yaml/yaml_typeIDs.html">[1]</a>
                </sup>
            </td>
            <td>Clone type ID. <em>(deprecated)<em></td>
        </tr>
        <tr>
            <td></td>
            <td>locationID</td>
            <td><strong>long</strong></td>
            <td>Clone location ID.</td>
        </tr>
        <tr>
            <td></td>
            <td>cloneName</td>
            <td><strong>string</strong></td>
            <td>Name given to clone.</td>
        </tr>
        <tr>
            <td>jumpCloneImplants</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing one row per jump clone implant.</td>
        </tr>
        <tr>
            <td></td>
            <td>jumpCloneID</td>
            <td><strong>long</strong></td>
            <td>Unique jump clone identifier.</td>
        </tr>
        <tr>
            <td></td>
            <td>typeID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/yaml/yaml_typeIDs.html">[1]</a>
                </sup>
            </td>
            <td>Type ID for implant</td>
        </tr>
        <tr>
            <td></td>
            <td>typeName</td>
            <td><strong>string</strong></td>
            <td>Name for implant.</td>
        </tr>
        <tr>
            <td>jumpActivation</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Last capital jump activation for character.</td>
        </tr>
        <tr>
            <td>jumpFatigue</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Jump fatigue expiry date for character.</td>
        </tr>
        <tr>
            <td>jumpLastUpdate</td>
            <td><strong>datetime</strong></td>
            <td></td>
            <td>Last jump update for character.</td>
        </tr>
    </tbody>
</table>

### Notes

* This call returns a subset of the information available in the <a href="../char_charactersheet.html">CharacterSheet</a> endpoint, but with a different mask so that API keys can be configured to only return clone and attribute information.  That is, if an API key allows <a href="../char_charactersheet.html">CharacterSheet</a>, then calling the Clones endpoint is unnecessary.

