# IndustryJobsHistory
Retrieve finished corporation industry jobs.

* __Path:__ ``/corp/IndustryJobsHistory.xml.aspx``
* __Cache timer:__ 6 hours
* __Access mask:__ 128
* __Parameters:__ none

### Sample Response

```xml
<result>
    <rowset name="jobs" key="jobID" columns="jobID,installerID,installerName,facilityID,solarSystemID,solarSystemName,stationID,activityID,blueprintID,blueprintTypeID,blueprintTypeName,blueprintLocationID,outputLocationID,runs,cost,teamID,licensedRuns,probability,productTypeID,productTypeName,status,timeInSeconds,startDate,endDate,pauseDate,completedDate,completedCharacterID,successfulRuns">
        <row jobID="229136101" installerID="498338451" installerName="Qoi" facilityID="60006382" solarSystemID="30005194" 
             solarSystemName="Cleyd" stationID="60006382" activityID="1" blueprintID="1015116533326"
             blueprintTypeID="2047" blueprintTypeName="Damage Control I Blueprint" blueprintLocationID="60006382" 
             outputLocationID="60006382" runs="1" cost="118.00" teamID="0" licensedRuns="200" probability="0"
             productTypeID="0" productTypeName="" status="1" timeInSeconds="548"
             startDate="2014-07-19 15:47:06" endDate="2014-07-19 15:56:14" pauseDate="0001-01-01 00:00:00"
             completedDate="0001-01-01 00:00:00" completedCharacterID="0" successfulRuns="1"/>
        <row jobID="229135883" installerID="498338451" installerName="Qoi" facilityID="60006382" solarSystemID="30005194"
             solarSystemName="Cleyd" stationID="60006382" activityID="3" blueprintID="1015321999447" 
             blueprintTypeID="25862" blueprintTypeName="Salvager I Blueprint" blueprintLocationID="60006382" 
             outputLocationID="60006382" runs="1" cost="29.00" teamID="0" licensedRuns="60" probability="0" 
             productTypeID="0" productTypeName="" status="1" timeInSeconds="702" 
             startDate="2014-07-19 13:40:59" endDate="2014-07-19 13:52:41" pauseDate="0001-01-01 00:00:00" 
             completedDate="0001-01-01 00:00:00" completedCharacterID="0" successfulRuns="2"/>
        <row jobID="229135882" installerID="498338451" installerName="Qoi" facilityID="60006382" solarSystemID="30005194" 
             solarSystemName="Cleyd" stationID="60006382" activityID="4" blueprintID="1015322244720" 
             blueprintTypeID="785" blueprintTypeName="Miner I Blueprint" blueprintLocationID="60006382" 
             outputLocationID="60006382" runs="1" cost="8.00" teamID="0" licensedRuns="200" probability="0" 
             productTypeID="0" productTypeName="" status="1" timeInSeconds="225" 
             startDate="2014-07-19 13:40:32" endDate="2014-07-19 13:44:17" pauseDate="0001-01-01 00:00:00" 
             completedDate="0001-01-01 00:00:00" completedCharacterID="0" successfulRuns="3"/>
        <row jobID="229135868" installerID="498338451" installerName="Qoi" facilityID="60006382" solarSystemID="30005194" 
             solarSystemName="Cleyd" stationID="60006382" activityID="5" blueprintID="1015322013688" blueprintTypeID="10040" 
             blueprintTypeName="Civilian Shield Booster Blueprint" blueprintLocationID="60006382" 
             outputLocationID="60006382" runs="23" cost="2768.00" teamID="0" licensedRuns="99" probability="0" 
             productTypeID="0" productTypeName="" status="1" timeInSeconds="389367" 
             startDate="2014-07-19 13:22:51" endDate="2014-07-24 01:32:18" pauseDate="0001-01-01 00:00:00" 
             completedDate="0001-01-01 00:00:00" completedCharacterID="0" successfulRuns="4"/>
        <row jobID="229136102" installerID="498338451" installerName="Qoi" facilityID="1015338129652" solarSystemID="30005195"
             solarSystemName="Vecamia" stationID="1015338119317" activityID="7" blueprintID="1015338143203" blueprintTypeID="30614"
             blueprintTypeName="Intact Armor Nanobot" blueprintLocationID="1015338129652"
             outputLocationID="1015338129652" runs="1" cost="641.00" teamID="0" licensedRuns="300" probability="0"
             productTypeID="0" productTypeName="" status="1" timeInSeconds="3600"
             startDate="2014-07-19 15:48:33" endDate="2014-07-19 16:48:33" pauseDate="0001-01-01 00:00:00"
             completedDate="0001-01-01 00:00:00" completedCharacterID="0" successfulRuns="5"/>
        <row jobID="229136071" installerID="498338451" installerName="Qoi" facilityID="1015338129650" solarSystemID="30005195" 
             solarSystemName="Vecamia" stationID="1015338119317" activityID="8" blueprintID="1015338137468" blueprintTypeID="1137" 
             blueprintTypeName="Antimatter Charge S Blueprint" blueprintLocationID="1015338129650"
             outputLocationID="1015338129650" runs="1" cost="4.00" teamID="0" licensedRuns="600" probability="0" 
             productTypeID="0" productTypeName="" status="1" timeInSeconds="11400" 
             startDate="2014-07-19 15:22:40" endDate="2014-07-19 18:32:40" pauseDate="0001-01-01 00:00:00" 
             completedDate="0001-01-01 00:00:00" completedCharacterID="0" successfulRuns="6"/>
    </rowset>
</result>
```

### Result Data

<table border="1">
    <tbody>
        <tr>
            <td>jobs</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing 1 row per industry job.</td>
        </tr>
        <tr>
            <td></td>
            <td>jobID</td>
            <td><strong>long</strong></td>
            <td>Unique job ID.</td>
        </tr>
        <tr>
            <td></td>
            <td>installerID</td>
            <td><strong>long</strong></td>
            <td>Character ID of the character which installed this job.</td>
        </tr>
        <tr>
            <td></td>
            <td>installerName</td>
            <td><strong>char</strong></td>
            <td>Name of character which installed this job.</td>
        </tr>
        <tr>
            <td></td>
            <td>facilityID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_invItems.html#itemID" title="invItems.itemID">[1]</a>,
                    <a href="../corporation/corp_facilities.html">[2]</a>,
                    <a href="../../crest/eve/eve_industryFacilities.html">[3]</a>
                </sup>
            </td>
            <td>Facility ID where this job is running (see cross-references).</td>
        </tr>
        <tr>
            <td></td>
            <td>solarSystemID</td>
            <td>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/sqlite/sqlite_mapSolarSystems.html#solarSystemID" title="mapSolarSystems.solarSystemID">[1]</a>
                </sup>
            </td>
            <td>Solar system where facility is located.</td>
        </tr>
        <tr>
            <td></td>
            <td>solarSystemName</td>
            <td><strong>string</strong></td>
            <td>Name of solar system where facility is located.</td>
        </tr>
        <tr>
            <td></td>
            <td>stationID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_invNames.html#itemID" title="invNames.itemID">[1]</a>,
                    <a href="../../sde/mssql/mssql_invItems.html#itemID" title="invItems.itemID">[2]</a>,
                    <a href="../../sde/mssql/mssql_invPositions.html#itemID" title="invPositions.itemID">[3]</a>,
                    <a href="../../sde/mssql/mssql_invUniqueNames.html#itemID" title="invUniqueNames.itemID">[4]</a>
                </sup>
            </td>
            <td>Station ID where industry facility is located.</td>
        </tr>
        <tr>
            <td></td>
            <td>activityID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_ramActivities.html#activityID" title="ramActivities.activityID">[1]</a>
                </sup>
            </td>
            <td>Job activity ID (see cross-reference).</td>
        </tr>
        <tr>
            <td></td>
            <td>blueprintID</td>
            <td nowrap>
                <strong>long</strong>
                <sup>
                    <a href="corp_assetlist.html">[1]</a>
                </sup>
            </td>
            <td>Blueprint asset item ID.</td>
        </tr>
        <tr>
            <td></td>
            <td>blueprintTypeID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/yaml/yaml_typeIDs.html">[1]</a>,
                    <a href="../../sde/mssql/mssql_invItems.html#typeID" title="invItems.typeID">[2]</a>,
                    <a href="../../sde/mssql/mssql_invMetaTypes.html#typeID" title="invMetaTypes.typeID">[3]</a>,
                    <a href="../../sde/mssql/mssql_invTypeMaterials.html#typeID" title="invTypeMaterials.typeID">[4]</a>,
                    <a href="../../sde/mssql/mssql_invTypeReactions.html#typeID" title="invTypeReactions.typeID">[5]</a>
                </sup>
            </td>
            <td>Blueprint type ID.</td>
        </tr>
        <tr>
            <td></td>
            <td>blueprintTypeName</td>
            <td><strong>char</strong></td>
            <td>Name of installed blueprint.</td>
        </tr>
        <tr>
            <td></td>
            <td>blueprintLocationID</td>
            <td><strong>int</strong></td>
            <td>Location ID of the location from which the blueprint was installed.  Normally a station ID, but can also be an asset (e.g. container) or corporation facility.</td>
        </tr>
        <tr>
            <td></td>
            <td>outputLocationID</td>
            <td><strong>int</strong></td>
            <td>Location ID of the location to which the output of the job will be delivered.  Normally a station ID, but can also be a corporation facility.</td>
        </tr>
        <tr>
            <td></td>
            <td>runs</td>
            <td><strong>int</strong></td>
            <td>Number of runs for a manufacturing job, or number of copies to make for a blueprint copy.</td>
        </tr>
        <tr>
            <td></td>
            <td>cost</td>
            <td><strong>decimal</strong></td>
            <td>The sume of job installation fee and industry facility tax.</td>
        </tr>
        <tr>
            <td></td>
            <td>teamID</td>
            <td><strong>int</strong></td>
            <td>N/A - retired in Proteus</td>
        </tr>
        <tr>
            <td></td>
            <td>licensedRuns</td>
            <td><strong>int</strong></td>
            <td>Number of runs blueprint is licensed for.</td>
        </tr>
        <tr>
            <td></td>
            <td>probability</td>
            <td><strong>float</strong></td>
            <td>Chance of success for invention.</td>
        </tr>
        <tr>
            <td></td>
            <td>productTypeID</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/yaml/yaml_typeIDs.html">[1]</a>,
                    <a href="../../sde/mssql/mssql_invItems.html#typeID" title="invItems.typeID">[2]</a>,
                    <a href="../../sde/mssql/mssql_invMetaTypes.html#typeID" title="invMetaTypes.typeID">[3]</a>,
                    <a href="../../sde/mssql/mssql_invTypeMaterials.html#typeID" title="invTypeMaterials.typeID">[4]</a>,
                    <a href="../../sde/mssql/mssql_invTypeReactions.html#typeID" title="invTypeReactions.typeID">[5]</a>
                </sup>
	    </td>
            <td>Type ID of product (manufactured, copied or invented).</td>
        </tr>
        <tr>
            <td></td>
            <td>productTypeName</td>
            <td><strong>string</strong></td>
            <td>Type name of product (manufactured, copied or invented).</td>
        </tr>
        <tr>
            <td></td>
            <td>status</td>
            <td nowrap>
                <strong>int</strong>
                <sup>
                    <a href="../constants.html#industry-job-status">[1]</a>
                </sup>
            </td>
            <td>Job status (see cross-reference).</td>
        </tr>
        <tr>
            <td></td>
            <td>timeInSeconds</td>
            <td><strong>int</strong></td>
            <td>Job duration in seconds.</td>
        </tr>
        <tr>
            <td></td>
            <td>startDate</td>
            <td><strong>datetime</strong></td>
            <td>Time when this job started.</td>
        </tr>
        <tr>
            <td></td>
            <td>endDate</td>
            <td><strong>datetime</strong></td>
            <td>Time when this job finished.</td>
        </tr>
        <tr>
            <td></td>
            <td>pauseDate</td>
            <td><strong>datetime</strong></td>
            <td>Time when this job was paused (e.g. time when the facility where this job was installed went offline).</td>
        </tr>
        <tr>
            <td></td>
            <td>completedDate</td>
            <td><strong>datetime</strong></td>
            <td>Time when this job was completed.</td>
        </tr>
        <tr>
            <td></td>
            <td>completedCharacterID</td>
            <td><strong>long</strong></td>
            <td>Character ID of character which completed this job.</td>
        </tr>
        <tr>
            <td></td>
            <td>successfulRuns</td>
            <td><strong>int</strong></td>
            <td>Number of successful runs for this job.  Equal to runs unless this is an invention job.</td>
        </tr>	
    </tbody>
</table>

### Notes

* This endpoint returns finished corporation jobs (e.g. started from a corporation hangar).  Use <a href="../../xmlapi/corporation/corp_industryjobs.html">Corporation - IndustryJobs</a> to retrieve unfinished jobs.
* This endpoint returns a maximum of 10000 rows and at most 90 days worth of data.
* If a job is cancelled manually, then the completedCharacterID identifies the character who cancelled the job.
* If a job is cancelled because the facility was unanchored, then completedCharacterID is 0.

### Known Bugs

* The licensedRuns field is showing undefined values for Manufacturing from a BPO, Reverse Engineering, Invention, ME, TE research.
* productTypeID and productTypeName for invention jobs with only one possible output type will remain empty until the job finishes.
* Status does not appear to change for a "ready" job, you must inspect timestamps to find when the job finishes.


