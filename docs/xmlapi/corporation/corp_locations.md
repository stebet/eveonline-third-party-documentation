# Locations
Returns location of an item or character.

* __Path:__ ``/corp/Locations.xml.aspx``
* __Cache timer:__ 1 hour
* __Access mask:__ 16777216
* __Parameters:__
	<table border="1">
	  <tbody>
            <tr>
                <th>Argument</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
             <tr>
                <td>ids</td>
                <td><strong>long</strong></td>
                <td>IDs of items to retrieve location information for</td>
            </tr>
	  </tbody>
	</table>

### Sample Response
```xml
<result>
  <rowset name="locations" key="itemID" columns="itemID,itemName,x,y,z">
    <row itemID="1020171077193" itemName="Gallente Control Tower" x="-67142925360" y="-8145422240" z="-1403156520"/>
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
            <td>itemID</td>
            <td>long</td>
            <td>ID of the item</td>
        </tr>
        <tr>
            <td>itemName</td>
            <td>string</td>
            <td>Name of the item</td>
        </tr>
        <tr>
            <td>x</td>
            <td>long</td>
            <td>X coordinate</td>
        </tr>
        <tr>
            <td>y</td>
            <td>long</td>
            <td>Y coordinate</td>
        </tr>
        <tr>
            <td>z</td>
            <td>long</td>
            <td>Z coordinate</td>
        </tr>
    </tbody>
</table>
