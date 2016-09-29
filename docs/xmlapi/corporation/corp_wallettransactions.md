# WalletTransactions
Retrieve corporation wallet transactions.
  
* __Path:__ ``/corp/WalletTransactions.xml.aspx``
* __Cache timer:__ 30 minutes
* __Access mask:__ 2097152
* __Parameters:__
    <table border="1">
        <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
            <tr>
                <td>accountKey</td>
                <td><strong>int</strong></td>
                <td>
                Account key of the wallet for which transactions will be returned.  Corporations have seven wallets numbered from 1000 through 1006.  
                The <a href="corp_accountbalance.html">Corporation - AccountBalance</a> call can be used to map corporation wallet to appropriate accountKey.
                </td>
            </tr>
            <tr>
                <td>fromID</td>
                <td><strong>long</strong></td>
                <td>
                Optional upper bound for the transaction ID of returned transactions.  This argument is normally used to walk to the transaction log backwards.
                See <a href="../intro.html#journal-walking">Journal Walking</a> for more information.
                </td>
            </tr>
            <tr>
                <td>rowCount</td>
                <td><strong>int</strong></td>
                <td>
                Optional limit on number of rows to return.  Default is 1000.  Maximum is 2560.
                </td>
            </tr>
        </tbody>
    </table>
    
### Sample Response

```xml
<result>
    <rowset name="transactions" key="transactionID" columns="transactionDateTime,transactionID,quantity,typeName,typeID,price,clientID,clientName,characterID,characterName,stationID,stationName,transactionType,transactionFor,journalTransactionID">
        <row transactionDateTime="2012-11-20 00:44:39" transactionID="2655168130" quantity="1" typeName="800mm Heavy Carbine Repeating Howitzer I" typeID="9329" price="625000.00" clientID="1112594762" clientName="Smedoc" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6599206786" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 17:13:18" transactionID="2656299632" quantity="1" typeName="Large Rudimentary Concussion Bomb I" typeID="9668" price="1075000.00" clientID="92561495" clientName="Sky Blazed" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6604731054" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 19:38:04" transactionID="2656400048" quantity="5" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="91750778" clientName="Juno Libertas" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605221409" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 19:44:32" transactionID="2656404846" quantity="10" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="91339209" clientName="Kai Cross" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605244403" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 19:46:35" transactionID="2656406483" quantity="5" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="1181049174" clientName="Kagerns" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605252986" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 20:14:10" transactionID="2656425787" quantity="6" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="608953610" clientName="PUNKYY" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605349273" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 20:35:56" transactionID="2656440644" quantity="5" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="1508173332" clientName="Hasentaenzer" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605426606" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 20:40:54" transactionID="2656444190" quantity="2" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="1337140157" clientName="Calcius Revolver" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605444557" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 21:01:35" transactionID="2656458693" quantity="2" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="1893909101" clientName="Constapatris" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605516695" clientTypeID="1377" />
        <row transactionDateTime="2012-11-21 22:11:47" transactionID="2656506286" quantity="6" typeName="Hobgoblin II" typeID="2456" price="475000.00" clientID="92328042" clientName="Haruchai Ardenol" characterID="90251444" characterName="trek apace" stationID="60005686" stationName="Hek VIII - Moon 12 - Boundless Creation Factory" transactionType="sell" transactionFor="corporation" journalTransactionID="6605751393" clientTypeID="1377" />
    </rowset>
</result>
```

### Result Data

<table border="1">
    <tbody>
        <tr>
            <td>transactions</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing 1 row per journal transaction.</td>
        </tr>
        <tr>
            <td></td>
            <td>transactionDateTime</td>
            <td><strong>datetime</strong></td>
            <td>Date and time of transaction.</td>
        </tr>
        <tr>
            <td></td>
            <td>transactionID</td>
            <td><strong>long</strong></td>
            <td>Unique tranaction ID.</td>
        </tr>
        <tr>
            <td></td>
            <td>quantity</td>
            <td><strong>int</strong></td>
            <td>Number of items bought or sold.</td>
        </tr>
        <tr>
            <td></td>
            <td>typeName</td>
            <td><strong>string</strong></td>
            <td>Name of item bought or sold.</td>
        </tr>
        <tr>
            <td></td>
            <td>typeID</td>
            <td>
                <strong>int</strong>
                <sup>
                    <a href="../../sde/yaml/yaml_typeIDs.html" title="Inventory Types file">[1]</a>
                </sup>
            </td>
            <td>Type ID of item bought or sold.</td>
        </tr>
        <tr>
            <td></td>
            <td>price</td>
            <td><strong>decimal</strong></td>
            <td>Amount paid per unit.</td>
        </tr>
        <tr>
            <td></td>
            <td>clientID</td>
            <td>
                <strong>long</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_crpNPCCorporations.html" title="NPC Corporations table when counterparty is an NPC Corporation">[1]</a>
                </sup>
            </td>
            <td>Counterparty character or corporation ID.  For NPC corporations, see the appropriate cross reference.</td>
        </tr>
        <tr>
            <td></td>
            <td>clientName</td>
            <td><strong>string</strong></td>
            <td>Counterparty name.</td>
        </tr>
        <tr>
            <td></td>
            <td>characterID</td>
            <td><strong>long</strong></td>
            <td>Character ID of character which represented corporation in transaction.</td>
        </tr>
        <tr>
            <td></td>
            <td>characterName</td>
            <td><strong>string</strong></td>
            <td>Character name of character which represented corporation in transaction.</td>
        </tr>
        <tr>
            <td></td>
            <td>stationID</td>
            <td>
                <strong>long</strong>
                <sup>
                    <a href="../../sde/mssql/mssql_staStations.html" title="Stations table">[1]</a>
                </sup>
            </td>
            <td>Station ID in which transaction took place.</td>
        </tr>
        <tr>
            <td></td>
            <td>stationName</td>
            <td><strong>string</strong></td>
            <td>Name of station in which transaction took place.</td>
        </tr>
        <tr>
            <td></td>
            <td>transactionType</td>
            <td><strong>string</strong></td>
            <td>Either "buy" or "sell" as appropriate.</td>
        </tr>
        <tr>
            <td></td>
            <td>transactionFor</td>
            <td><strong>string</strong></td>
            <td>Either "personal" or "corporate" as appropriate.</td>
        </tr>
        <tr>
            <td></td>
            <td>journalTransactionID</td>
            <td>
                <strong>long</strong>
                <sup>
                    <a href="corp_walletjournal.html" title="Stations table">[1]</a>
                </sup>
            </td>
            <td>Corresponding wallet journal refID.</td>
        </tr>
        <tr>
            <td></td>
            <td>clientTypeID</td>
            <td>
                <strong>long</strong>
                <sup>
                    <a href="../eve/eve_typename.html" title="Type name">[1]</a>
                </sup>
            </td>
            <td>Type ID of the counterparty.</td>
        </tr>
    </tbody>
</table>

