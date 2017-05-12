# AccountBalance
Retrieve corporation account balances.

* __Path:__ ``/corp/AccountBalance.xml.aspx``
* __Cache timer:__ 15 minutes
* __Access mask:__ 1
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
                <td>ID of accessing character (must have junior accountant access or higher in the character's corporation). Only used with legacy API keys.</td>
            </tr>
        </tbody>
    </table>

### Sample Response

```xml
<eveapi version="2">
    <currentTime>2015-05-06 17:00:11</currentTime>
        <result>
            <rowset name="accounts" key="accountID" columns="accountID,accountKey,balance">
                <row accountID="40192049" accountKey="1000" balance="7140579224.62" />
                <row accountID="40211102" accountKey="1001" balance="0.00" />
                <row accountID="40211103" accountKey="1002" balance="0.00" />
                <row accountID="40211104" accountKey="1003" balance="0.00" />
                <row accountID="40211105" accountKey="1004" balance="0.00" />
                <row accountID="40211106" accountKey="1005" balance="0.00" />
                <row accountID="40211107" accountKey="1006" balance="0.00" />
            </rowset>
        </result>
    <cachedUntil>2015-05-06 17:15:11</cachedUntil>
</eveapi>
```  

### Result Data

<table border="1">
    <tbody>
        <tr>
            <th>Name</th>
            <th>Data type</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>accountID</td>
            <td>int</td>
            <td>ID of the account</td>
        </tr>
        <tr>
            <td>accountKey</td>
            <td>int</td>
            <td>Account identifier</td>
        </tr>
        <tr>
            <td>balance</td>
            <td>decimal</td>
            <td>Amount of ISK in this corporation wallet</td>
        </tr>
    </tbody>
</table>

### Notes

* __accountKey:__ This is always 1000 for a character's account balance as opposed to a corporation, where accountKey ranges from 1000 to 1006 for the seven corporate wallet divisions.
