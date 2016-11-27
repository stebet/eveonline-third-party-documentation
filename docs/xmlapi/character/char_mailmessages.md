# MailMessages
Returns the header of eve mail messages sent to the character.

* __Path:__ ``/char/MailMessages.xml.aspx``
* __Cache timer:__ 15 minutes
* __Access mask:__ 2048
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
                <td>ID of character</td>
            </tr>
        </tbody>
    </table>

### Sample Response

```xml
<result>
    <rowset name="messages" key="messageID" columns="messageID,senderID,senderName,sentDate,title,toCorpOrAllianceID,toCharacterIDs,toListID">
        <row messageID="290285276" senderID="999999999" senderName="Some guy" sentDate="2009-12-01 01:04:00" title="Corp mail" toCorpOrAllianceID="999999999" toCharacterIDs="" toListID="" />
        <row messageID="290285275" senderID="999999999" senderName="Some guy" sentDate="2009-12-01 01:04:00" title="Personal mail" toCorpOrAllianceID="" toCharacterIDs="999999999" toListID="" />
        <row messageID="290285274" senderID="999999999" senderName="Some guy" sentDate="2009-12-01 01:04:00" title="Message to mailing list" toCorpOrAllianceID="" toCharacterIDs="" toListID="999999999" />
    </rowset>
</result>
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
            <td>messageID</td>
            <td>int</td>
            <td>The unique message ID number.</td>
        </tr>
        <tr>
            <td>senderID</td>
            <td>int</td>
            <td>The character ID or Mailing List ID of the message originator.</td>
        </tr>
        <tr>
            <td>senderName</td>
            <td>string</td>
            <td>The character name or Mailing List name of the message originator.</td>
        </tr>
        <tr>
            <td>sentDate</td>
            <td>date string</td>
            <td>The date the message was sent.</td>
        </tr>
        <tr>
            <td>title</td>
            <td>string</td>
            <td>The title/subject of the message</td>
        </tr>
        <tr>
            <td>toCorpOrAllianceID</td>
            <td>int</td>
            <td>The ID of a corporation/alliance that the message was sent to.</td>
        </tr>
        <tr>
            <td>toCharacterIDs</td>
            <td>string</td>
            <td>Comma-separated list of character IDs of the characters that received the message.</td>
        </tr>
        <tr>
            <td>toListID</td>
            <td>string</td>
            <td>Comma-separated list of mailing lists that the mail was sent to. Currently you can only send a mail to one list but that might change so we made this a list instead of a single ID. The IDs of lists the character is subscribed to can be resolved using the <a href="char_mailinglists.html">Character - MailingLists</a>.</td>
        </tr>
    </tbody>
</table>

### Notes

* The first request returns the latest 50 mails/200 notifications sent or received by the character within the last 10 days. Older items are skipped.
* Subsequent requests return only the new items received since the last request.
* You can request new items every 30 minutes.
* If you want to re-set the timer and get the first-request bulk again, you'll have to wait 6 hours.
