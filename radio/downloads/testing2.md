---
title: I AM A NEW PAGE
categories:
  - radio
date: 2012-10-19 13:48:54 +0500
---
{% include box-open.html box-id="4563" title="testing part 2:" author-id="5884" timestamp="2012-10-19 13:48:54 +0500" type="norm" dbname="box20658" last-modified-by="127" %}
Downloads are available for a number of shows that the DJs have done for Radio PSI! (A large number of shows are, unfortunately, missing.) Click a link below to open a new page full of downloadable archives from your favorite DJ! Archives are added to these lists noon Eastern, the day after broadcast.

<br /><br />Load archives for:
<br /><input type="button" value="Current DJs" onClick="
var djNames=new Array('amztrak_twih','amztrak_tog', 'Aquas', 'alchemist', 'eggstreme', 'kame', 'mon', 'pollyanna', 'umbra');
var showNames=new Array('DJ Amztrak: This Week in History','DJ Amztrak: Throne of Games', 'DJ Aquazition', 'Edo the DJ Alchemist', 'The DJ Eggstreme Program', 'Miss Kame', 'DJ Mon - Digital Monsters', 'DJ Pollyanna', 'DJ Umbra and the Shadow Waves of Radio');
var quote=document.getElementById('charList').innerHTML.charAt(7);
var lessThan=document.getElementById('charList').innerHTML.charAt(0);
var greaterThan=document.getElementById('charList').innerHTML.charAt(2);
var newHTML='';

document.getElementById('djType').innerHTML='Current DJs';

for (var i=djNames.length-1;i!=-1;i--) { 

newHTML=(lessThan+'a onClick='+quote+'document.getElementById(\'archiveList\').src = \'http://radio.fobby.net/dumps/archives/archives.php?dj='+djNames[i]+'\'; document.getElementById(\'archivesFor\').innerHTML=\''+showNames[i]+'\';'+quote+greaterThan+showNames[i]+lessThan+'/a'+greaterThan+lessThan+'BR />\n'+newHTML);

}

document.getElementById('djList').innerHTML=(newHTML);

" />

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<input type="button" value="Retired DJs" onClick="

var djNames=new Array('beta', 'gamma', 'brewster', 'dex', 'jamiemen', 'notadj', 'ozztastic', 'sephg', 'showdax', 'simonroberts', 'tansunn', 'glasses', 'carparama');
var showNames=new Array('DJ Beta', 'DJ Gamma', 'DJ Brewster', 'DJ Dex', 'DJ Jamie Men', 'DJ Not-a-DJ', 'DJ ozztastic', 'DJ Seph G', 'DJ Showdax', 'DJ Simon Roberts', 'DJ Tanner', 'DJ Wilhelmina','DJ Carparama, DJ Jetski Epicmount, Team Kobaugh, DJ Whatever Randy is Calling Himself This Week');

var quote=document.getElementById('charList').innerHTML.charAt(7);
var lessThan=document.getElementById('charList').innerHTML.charAt(0);
var greaterThan=document.getElementById('charList').innerHTML.charAt(2);
var newHTML='';

document.getElementById('djType').innerHTML='Retired DJs';

for (var i=djNames.length-1;i!=-1;i--) { 

newHTML=(lessThan+'a onClick='+quote+'document.getElementById(\'archiveList\').src = \'http://radio.fobby.net/dumps/archives/archives.php?dj='+djNames[i]+'\'; document.getElementById(\'archivesFor\').innerHTML=\''+showNames[i]+'\';'+quote+greaterThan+showNames[i]+lessThan+'/a'+greaterThan+lessThan+'BR />\n'+newHTML);

}

document.getElementById('djList').innerHTML=(newHTML);

" />

<br /><br /><span id="charList"><b></b>"Retired" DJs archives not available for: DJ Fly-Boi Mathyz</span>

<br />
<br /><table>
<tr>
<td valign="top" width="400">


<br /><span id="djType" style="font-size:1.5em"></span>

<br />
<br /><span id="djList"></span>

</td>

<td style="width:100;">
<span id="archivesFor">Choose a DJ</span>
<br /><iframe id="archiveList" height="300" width="100%" scrolling="auto" seamless="seamless" />
</td>
</tr>
</table>
{% include box-close.html author-name="cyan683" last-modified-on="2012-10-22 15:49:53 +0500" last-modified-by-name="cyan683" %}
