# Notifications
Retrieve character notification headers.

* __Path:__ ``/char/Notifications.xml.aspx``
* __Cache timer:__ 30 minutes
* __Access mask:__ 16384
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
            <td>Character ID for which notification headers will be retrieved</td>
        </tr>
    </tbody>
</table>

### Sample Response

```xml
<result>
  <rowset name="notifications" key="notificationID" columns="notificationID,typeID,senderID,senderName,sentDate,read">
    <row notificationID="399058968" typeID="73" senderID="3017794" senderName="Some guy" sentDate="2012-12-22 23:34:00" read="0" />
  </rowset>
</result>
```  

### Result Data

<table border="1">
    <tbody>
        <tr>
            <td>notifications</td>
            <td><strong>rowset</strong></td>
            <td></td>
            <td>Rowset containing 1 row per notification header.</td>
        </tr>
        <tr>
            <td></td>
            <td>notificationID</td>
            <td><strong>long</strong></td>
            <td>Unique notification ID.</td>
        </tr>
        <tr>
            <td></td>
            <td>typeID</td>
            <td>
                <strong>int</strong>
                <sup>
                    <a href="../constants.html#notification-type">[1]</a>
                </sup>
            </td>
            <td>Type ID describing the notification.</td>
        </tr>
        <tr>
            <td></td>
            <td>senderID</td>
            <td><strong>long</strong></td>
            <td>ID of entity which sent notification.</td>
        </tr>
        <tr>
            <td></td>
            <td>senderName</td>
            <td><strong>string</strong></td>
            <td>Name of entity which sent notification.</td>
        </tr>
        <tr>
            <td></td>
            <td>sentDate</td>
            <td><strong>datetime</strong></td>
            <td>Date when notification was sent.</td>
        </tr>
        <tr>
            <td></td>
            <td>read</td>
            <td><strong>boolean</strong></td>
            <td>1 if this notification has been read in the EVE client, 0 otherwise.</td>
        </tr>
    </tbody>
</table>

### Notification Types

<table border="1">
    <thead>
        <tr>
            <th>TypeID</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>  
        <tr>
            <td align="right">1</td>
            <td>Legacy</td>
        </tr>
        <tr>
            <td align="right">2</td>
            <td>Character deleted</td>
        </tr>
        <tr>
            <td align="right">3</td>
            <td>Give medal to character</td>
        </tr>
        <tr>
            <td align="right">4</td>
            <td>Alliance maintenance bill</td>
        </tr>
        <tr>
            <td align="right">5</td>
            <td>Alliance war declared</td>
        </tr>
        <tr>
            <td align="right">6</td>
            <td>Alliance war surrender</td>
        </tr>
        <tr>
            <td align="right">7</td>
            <td>Alliance war retracted</td>
        </tr>
        <tr>
            <td align="right">8</td>
            <td>Alliance war invalidated by Concord</td>
        </tr>
        <tr>
            <td align="right">9</td>
            <td>Bill issued to a character</td>
        </tr>
        <tr>
            <td align="right">10</td>
            <td>Bill issued to corporation or alliance</td>
        </tr>
        <tr>
            <td align="right">11</td>
            <td>Bill not paid because there's not enough ISK available</td>
        </tr>
        <tr>
            <td align="right">12</td>
            <td>Bill, issued by a character, paid</td>
        </tr>
        <tr>
            <td align="right">13</td>
            <td>Bill, issued by a corporation or alliance, paid</td>
        </tr>
        <tr>
            <td align="right">14</td>
            <td>Bounty claimed</td>
        </tr>
        <tr>
            <td align="right">15</td>
            <td>Clone activated</td>
        </tr>
        <tr>
            <td align="right">16</td>
            <td>New corp member application</td>
        </tr>
        <tr>
            <td align="right">17</td>
            <td>Corp application rejected</td>
        </tr>
        <tr>
            <td align="right">18</td>
            <td>Corp application accepted</td>
        </tr>
        <tr>
            <td align="right">19</td>
            <td>Corp tax rate changed</td>
        </tr>
        <tr>
            <td align="right">20</td>
            <td>Corp news report, typically for shareholders</td>
        </tr>
        <tr>
            <td align="right">21</td>
            <td>Player leaves corp</td>
        </tr>
        <tr>
            <td align="right">22</td>
            <td>Corp news, new CEO</td>
        </tr>
        <tr>
            <td align="right">23</td>
            <td>Corp dividend/liquidation, sent to shareholders</td>
        </tr>
        <tr>
            <td align="right">24</td>
            <td>Corp dividend payout, sent to shareholders</td>
        </tr>
        <tr>
            <td align="right">25</td>
            <td>Corp vote created</td>
        </tr>
        <tr>
            <td align="right">26</td>
            <td>Corp CEO votes revoked during voting</td>
        </tr>
        <tr>
            <td align="right">27</td>
            <td>Corp declares war</td>
        </tr>
        <tr>
            <td align="right">28</td>
            <td>Corp war has started</td>
        </tr>
        <tr>
            <td align="right">29</td>
            <td>Corp surrenders war</td>
        </tr>
        <tr>
            <td align="right">30</td>
            <td>Corp retracts war</td>
        </tr>
        <tr>
            <td align="right">31</td>
            <td>Corp war invalidated by Concord</td>
        </tr>
        <tr>
            <td align="right">32</td>
            <td>Container password retrieval</td>
        </tr>
        <tr>
            <td align="right">33</td>
            <td>Contraband or low standings cause an attack or items being confiscated</td>
        </tr>
        <tr>
            <td align="right">34</td>
            <td>First ship insurance</td>
        </tr>
        <tr>
            <td align="right">35</td>
            <td>Ship destroyed, insurance payed</td>
        </tr>
        <tr>
            <td align="right">36</td>
            <td>Insurance contract invalidated/runs out</td>
        </tr>
        <tr>
            <td align="right">37</td>
            <td>Sovereignty claim fails (alliance)</td>
        </tr>
        <tr>
            <td align="right">38</td>
            <td>Sovereignty claim fails (corporation)</td>
        </tr>
        <tr>
            <td align="right">39</td>
            <td>Sovereignty bill late (alliance)</td>
        </tr>
        <tr>
            <td align="right">40</td>
            <td>Sovereignty bill late (corporation)</td>
        </tr>
        <tr>
            <td align="right">41</td>
            <td>Sovereignty claim lost (alliance)</td>
        </tr>
        <tr>
            <td align="right">42</td>
            <td>Sovereignty claim lost (corporation)</td>
        </tr>
        <tr>
            <td align="right">43</td>
            <td>Sovereignty claim acquired (alliance)</td>
        </tr>
        <tr>
            <td align="right">44</td>
            <td>Sovereignty claim acquired (corporation)</td>
        </tr>
        <tr>
            <td align="right">45</td>
            <td>Alliance anchoring alert</td>
        </tr>
        <tr>
            <td align="right">46</td>
            <td>Alliance structure turns vulnerable</td>
        </tr>
        <tr>
            <td align="right">47</td>
            <td>Alliance structure turns invulnerable</td>
        </tr>
        <tr>
            <td align="right">48</td>
            <td>Sovereignty disruptor anchored</td>
        </tr>
        <tr>
            <td align="right">49</td>
            <td>Structure won/lost</td>
        </tr>
        <tr>
            <td align="right">50</td>
            <td>Corp office lease expiration notice</td>
        </tr>
        <tr>
            <td align="right">51</td>
            <td>Clone contract revoked by station manager</td>
        </tr>
        <tr>
            <td align="right">52</td>
            <td>Corp member clones moved between stations</td>
        </tr>
        <tr>
            <td align="right">53</td>
            <td>Clone contract revoked by station manager</td>
        </tr>
        <tr>
            <td align="right">54</td>
            <td>Insurance contract expired</td>
        </tr>
        <tr>
            <td align="right">55</td>
            <td>Insurance contract issued</td>
        </tr>
        <tr>
            <td align="right">56</td>
            <td>Jump clone destroyed</td>
        </tr>
        <tr>
            <td align="right">57</td>
            <td>Jump clone destroyed</td>
        </tr>
        <tr>
            <td align="right">58</td>
            <td>Corporation joining factional warfare</td>
        </tr>
        <tr>
            <td align="right">59</td>
            <td>Corporation leaving factional warfare</td>
        </tr>
        <tr>
            <td align="right">60</td>
            <td>Corporation kicked from factional warfare on startup because of too low standing to the faction</td>
        </tr>
        <tr>
            <td align="right">61</td>
            <td>Character kicked from factional warfare on startup because of too low standing to the faction</td>
        </tr>
        <tr>
            <td align="right">62</td>
            <td>Corporation in factional warfare warned on startup because of too low standing to the faction</td>
        </tr>
        <tr>
            <td align="right">63</td>
            <td>Character in factional warfare warned on startup because of too low standing to the faction</td>
        </tr>
        <tr>
            <td align="right">64</td>
            <td>Character loses factional warfare rank</td>
        </tr>
        <tr>
            <td align="right">65</td>
            <td>Character gains factional warfare rank</td>
        </tr>
        <tr>
            <td align="right">66</td>
            <td>Agent has moved</td>
        </tr>
        <tr>
            <td align="right">67</td>
            <td>Mass transaction reversal message</td>
        </tr>
        <tr>
            <td align="right">68</td>
            <td>Reimbursement message</td>
        </tr>
        <tr>
            <td align="right">69</td>
            <td>Agent locates a character</td>
        </tr>
        <tr>
            <td align="right">70</td>
            <td>Research mission becomes available from an agent</td>
        </tr>
        <tr>
            <td align="right">71</td>
            <td>Agent mission offer expires</td>
        </tr>
        <tr>
            <td align="right">72</td>
            <td>Agent mission times out</td>
        </tr>
        <tr>
            <td align="right">73</td>
            <td>Agent offers a storyline mission</td>
        </tr>
        <tr>
            <td align="right">74</td>
            <td>Tutorial message sent on character creation</td>
        </tr>
        <tr>
            <td align="right">75</td>
            <td>Tower alert</td>
        </tr>
        <tr>
            <td align="right">76</td>
            <td>Tower resource alert</td>
        </tr>
        <tr>
            <td align="right">77</td>
            <td>Station aggression message</td>
        </tr>
        <tr>
            <td align="right">78</td>
            <td>Station state change message</td>
        </tr>
        <tr>
            <td align="right">79</td>
            <td>Station conquered message</td>
        </tr>
        <tr>
            <td align="right">80</td>
            <td>Station aggression message</td>
        </tr>
        <tr>
            <td align="right">81</td>
            <td>Corporation requests joining factional warfare</td>
        </tr>
        <tr>
            <td align="right">82</td>
            <td>Corporation requests leaving factional warfare</td>
        </tr>
        <tr>
            <td align="right">83</td>
            <td>Corporation withdrawing a request to join factional warfare</td>
        </tr>
        <tr>
            <td align="right">84</td>
            <td>Corporation withdrawing a request to leave factional warfare</td>
        </tr>
        <tr>
            <td align="right">85</td>
            <td>Corporation liquidation</td>
        </tr>
        <tr>
            <td align="right">86</td>
            <td>Territorial Claim Unit under attack</td>
        </tr>
        <tr>
            <td align="right">87</td>
            <td>Sovereignty Blockade Unit under attack</td>
        </tr>
        <tr>
            <td align="right">88</td>
            <td>Infrastructure Hub under attack</td>
        </tr>
        <tr>
            <td align="right">89</td>
            <td>Contact add notification</td>
        </tr>
        <tr>
            <td align="right">90</td>
            <td>Contact edit notification</td>
        </tr>
        <tr>
            <td align="right">91</td>
            <td>Incursion Completed</td>
        </tr>
        <tr>
            <td align="right">92</td>
            <td>Corp Kicked</td>
        </tr>
        <tr>
            <td align="right">93</td>
            <td>Customs office has been attacked</td>
        </tr>
        <tr>
            <td align="right">94</td>
            <td>Customs office has entered reinforced</td>
        </tr>
        <tr>
            <td align="right">95</td>
            <td>Customs office has been transferred</td>
        </tr>
        <tr>
            <td align="right">96</td>
            <td>FW Alliance Warning</td>
        </tr>
        <tr>
            <td align="right">97</td>
            <td>FW Alliance Kick</td>
        </tr>
        <tr>
            <td align="right">98</td>
            <td>AllWarCorpJoined Msg</td>
        </tr>
        <tr>
            <td align="right">99</td>
            <td>Ally Joined Defender</td>
        </tr>
        <tr>
            <td align="right">100</td>
            <td>Ally Has Joined a War Aggressor</td>
        </tr>
        <tr>
            <td align="right">101</td>
            <td>Ally Joined War Ally</td>
        </tr>
        <tr>
            <td align="right">102</td>
            <td>New war system: entity is offering assistance in a war.
            </td>
        </tr>
        <tr>
            <td align="right">103</td>
            <td>War Surrender Offer</td>
        </tr>
        <tr>
            <td align="right">104</td>
            <td>War Surrender Declined</td>
        </tr>
        <tr>
            <td align="right">105</td>
            <td>FacWar LP Payout Kill</td>
        </tr>
        <tr>
            <td align="right">106</td>
            <td>FacWar LP Payout Event</td>
        </tr>
        <tr>
            <td align="right">107</td>
            <td>FacWar LP Disqualified Eventd</td>
        </tr>
        <tr>
            <td align="right">108</td>
            <td>FacWar LP Disqualified Kill</td>
        </tr>
        <tr>
            <td align="right">109</td>
            <td>Alliance Contract Cancelled</td>
        </tr>
        <tr>
            <td align="right">110</td>
            <td>War Ally Declined Offer</td>
        </tr>
        <tr>
            <td align="right">111</td>
            <td>Your Bounty Was Claimed</td>
        </tr>
        <tr>
            <td align="right">112</td>
            <td>Bounty placed (Char)</td>
        </tr>
        <tr>
            <td align="right">113</td>
            <td>Bounty Placed (Corp)</td>
        </tr>
        <tr>
            <td align="right">114</td>
            <td>Bounty Placed (Alliance)</td>
        </tr>
        <tr>
            <td align="right">115</td>
            <td>Kill Right Available</td>
        </tr>
        <tr>
            <td align="right">116</td>
            <td>Kill right Available Open</td>
        </tr>
        <tr>
            <td align="right">117</td>
            <td>Kill Right Earned</td>
        </tr>
        <tr>
            <td align="right">118</td>
            <td>Kill right Used</td>
        </tr>
        <tr>
            <td align="right">119</td>
            <td>Kill Right Unavailable</td>
        </tr>
        <tr>
            <td align="right">120</td>
            <td>Kill Right Unavailable Open</td>
        </tr>
        <tr>
            <td align="right">121</td>
            <td>Declare War</td>
        </tr>
        <tr>
            <td align="right">122</td>
            <td>Offered Surrender</td>
        </tr>
        <tr>
            <td align="right">123</td>
            <td>Accepted Surrender</td>
        </tr>
        <tr>
            <td align="right">124</td>
            <td>Made War Mutual</td>
        </tr>
        <tr>
            <td align="right">125</td>
            <td>Retracts War</td>
        </tr>
        <tr>
            <td align="right">126</td>
            <td>Offered To Ally</td>
        </tr>
        <tr>
            <td align="right">127</td>
            <td>Accepted Ally</td>
        </tr>
        <tr>
            <td align="right">128</td>
            <td>Character Application Accept</td>
        </tr>
        <tr>
            <td align="right">129</td>
            <td>Character Application Reject</td>
        </tr>
        <tr>
            <td align="right">130</td>
            <td>Character Application Withdraw</td>
        </tr>
        <tr>
            <td align="right">138</td>
            <td>Clone activated</td>
        </tr>
        <tr>
            <td align="right">140</td>
            <td>Loss report available</td>
        </tr>
        <tr>
            <td align="right">141</td>
            <td>Kill report available</td>
        </tr>
        <tr>
            <td align="right">147</td>
            <td>Entosis Link started</td>
        </tr>
        <tr>
            <td align="right">148</td>
            <td>Entosis Link enabled a module</td>
        </tr>
        <tr>
            <td align="right">149</td>
            <td>Entosis Link disabled a module</td>
        </tr>
        <tr>
            <td align="right">131</td>
            <td>DustAppAcceptedMsg ?</td>
        </tr>
        <tr>
            <td align="right">132</td>
            <td>DistrictAttacked ?</td>
        </tr>
        <tr>
            <td align="right">133</td>
            <td>BattlePunishFriendlyFire ?</td>
        </tr>
        <tr>
            <td align="right">134</td>
            <td>BountyESSTaken ?</td>
        </tr>
        <tr>
            <td align="right">135</td>
            <td>BountyESSShared ?</td>
        </tr>
        <tr>
            <td align="right">136</td>
            <td>IndustryTeamAuctionWon ?</td>
        </tr>
        <tr>
            <td align="right">137</td>
            <td>IndustryTeamAuctionLost ?</td>
        </tr>
        <tr>
            <td align="right">139</td>
            <td>Corporation invitation accepted (CorpAppInvitedMsg)</td>
        </tr>
        <tr>
            <td align="right">142</td>
            <td>Corporation application rejected (CorpAppRejectCustomMsg)</td>
        </tr>
        <tr>
            <td align="right">143</td>
            <td>Friendly fire enable timer started (CorpFriendlyFireEnableTimerStarted)</td>
        </tr>
        <tr>
            <td align="right">144</td>
            <td>Friendly fire disable timer started (CorpFriendlyFireDisableTimerStarted)</td>
        </tr>
        <tr>
            <td align="right">145</td>
            <td>Friendly fire enable timer completed (CorpFriendlyFireEnableTimerCompleted)</td>
        </tr>
        <tr>
            <td align="right">146</td>
            <td>Friendly fire disable timer completed (CorpFriendlyFireDisableTimerCompleted)</td>
        </tr>
        <tr>
            <td align="right">152</td>
            <td>Infrastructure hub bill about to expire (InfrastructureHubBillAboutToExpire)</td>
        </tr>
        <tr>
            <td align="right">160</td>
            <td>Sovereignty structure reinforced (SovStructureReinforced)</td>
        </tr>
        <tr>
            <td align="right">161</td>
            <td>SovCommandNodeEventStarted ?</td>
        </tr>
        <tr>
            <td align="right">162</td>
            <td>Sovereignty structure destroyed (SovStructureDestroyed)</td>
        </tr>
        <tr>
            <td align="right">163</td>
            <td>SovStationEnteredFreeport ?</td>
        </tr>
        <tr>
            <td align="right">164</td>
            <td>IHubDestroyedByBillFailure ?</td>
        </tr>
        <tr>
            <td align="right">166</td>
            <td>BuddyConnectContactAdd ?</td>
        </tr>
        <tr>
            <td align="right">165</td>
            <td>Alliance capital changed (AllianceCapitalChanged)</td>
        </tr>
        <tr>
            <td align="right">167</td>
            <td>Sovereignty structure self destruction requested (SovStructureSelfDestructRequested)</td>
        </tr>
        <tr>
            <td align="right">168</td>
            <td>Sovereignty structure self destruction canceled (SovStructureSelfDestructCancel)</td>
        </tr>
        <tr>
            <td align="right">169</td>
            <td>Sovereignty structure self destruction completed (SovStructureSelfDestructFinished)</td>
        </tr>
        <tr>
            <td align="right">181</td>
            <td>Structure fuel alert (StructureFuelAlert)</td>
        </tr>
        <tr>
            <td align="right">182</td>
            <td>Structure anchoring started (StructureAnchoring)</td>
        </tr>
        <tr>
            <td align="right">183</td>
            <td>Structure unanchoring started (StructureUnanchoring)</td>
        </tr>
        <tr>
            <td align="right">184</td>
            <td>Structure under attack (StructureUnderAttack)</td>
        </tr>
        <tr>
            <td align="right">185</td>
            <td>Structure Online (StructureOnline)</td>
        </tr>
        <tr>
            <td align="right">186</td>
            <td>Structure lost shields (StructureLostShields)</td>
        </tr>
        <tr>
            <td align="right">187</td>
            <td>Structure lost Armor (StructureLostArmor)</td>
        </tr>
        <tr>
            <td align="right">188</td>
            <td>Structure destroyed (StructureDestroyed)</td>
        </tr>
        <tr>
            <td align="right">198</td>
            <td>Structure service offline (StructureServicesOffline)</td>
        </tr>
        <tr>
            <td align="right">199</td>
            <td>Item delivered (StructureItemsDelivered)</td>
        </tr>
        <tr>
            <td align="right">201</td>
            <td>StructureCourierContractChanged ?</td>
        </tr>
        <tr>
            <td align="right">1012</td>
            <td>OperationFinished ?</td>
        </tr>
        <tr>
            <td align="right">1030</td>
            <td>Game time received (GameTimeReceived)</td>
        </tr>
        <tr>
            <td align="right">1031</td>
            <td>Game time sent (GameTimeSent)</td>
        </tr>
    </tbody>
</table>

### Notes

* The first call to this endpoint returns the latest 200 notifications received by the character within the last week.
* Subsequent requests return only the new items received since the last request.
* You can request new items every 30 minutes.
* To "reset the timer" and retrieve from the start, you'll need to wait 6 hours before calling this endpoint.
