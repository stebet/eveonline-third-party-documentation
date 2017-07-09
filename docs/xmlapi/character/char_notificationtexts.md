# Notification Texts
Retrieve character notification bodies.

* __Path:__ ``/char/NotificationTexts.xml.aspx``
* __Cache timer:__ 10 years <sup style="color: red; font-weight: bold">(see notes below)</sup>
* __Access mask:__ 32768
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
                <td>Character ID for which notification texts will be retrieved</td>
            </tr>
            <tr>
                <td>IDs</td>
                <td>list of <strong>long</strong></td>
                <td>Comma separated list of notification IDs for which texts should be retrieved (see notes below)</td>
            </tr>
        </tbody>
    </table>

### Sample Response

```xml
<rowset name="notifications" key="notificationID" columns="notificationID">
    <row notificationID="374044083"><![CDATA[
        isHouseWarmingGift: 1
        shipTypeID: 606
    ]]></row>
    <row notificationID="374067406"><![CDATA[
        amount: 25000000
        dueDate: 129808158000000000
    ]]></row>
    <row notificationID="374106507"><![CDATA[
         againstID: 673381830
         cost: null
         declaredByID: 98105019
         delayHours: null
         hostileState: null
    ]]></row>
    <row notificationID="374119034"><![CDATA[
          aggressorAllianceID: 673381830
          aggressorCorpID: 785714366
          aggressorID: 1746208390
          armorValue: 1.0
          hullValue: 1.0
          moonID: 40264916
          shieldValue: 0.995
          solarSystemID: 30004181
          typeID: 16688
    ]]></row>
    <row notificationID="374133265"><![CDATA[
          amount: 5125528.4
          itemID: 1005888572647
          payout: 1
    ]]></row>
</rowset>
```  

### Result Data

<table border="1">
    <tbody>
        <tr>
            <td>notifications</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing 1 row per notification text.</td>
        </tr>
        <tr>
            <td></td>
            <td>notificationID</td>
            <td><strong>long</strong></td>
            <td>Unique notification ID corresponding to the following notification text.</td>
        </tr>
        <tr>
            <td></td>
            <td>notification text</td>
            <td><strong>CDATA</strong></td>
            <td>CDATA (character data) encoded notification text.  The contents of the text depend on the notification type ID (see <a href="../../xmlapi/constants.html/#notification-type">Notification Types</a>).</td>
        </tr>
    </tbody>
</table>

### Sample Response for Missing IDs

```xml
<result>
    <rowset name="notifications" key="notificationID" columns="notificationID">
        <missingIDs>1234,5678</missingIDs>
    </rowset>
</result>
```  

### Result Data for Missing IDs

<table border="1">
    <tbody>
        <tr>
            <td>notifications</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Contains a "missingIDs" child when some notification texts could not be retrieved.</td>
        </tr>
        <tr>
            <td></td>
            <td>missindIDs</td>
            <td>list of <strong>long</strong></td>
            <td>Comma separated list of notification IDs for which texts could not be retrieved.</td>
        </tr>
    </tbody>
</table>

### Notes

* Notification headers must be requested first before the corresponding notification texts can be retrieved.
* Notification texts typically report a "cached until" time of ten years from the current time.  It's not clear whether texts are really cached for this long.
* Some notification types have structured data in the corresponding notification text.  See <a href="../../xmlapi/constants.html#notification-type">Notification Types</a> for a description of this data.
