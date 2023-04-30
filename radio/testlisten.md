---
title: Radio PSI - How to Listen
categories:
  - radio
date: 2013-03-14 20:49:27 +0000
---
{% include box-open.html box-id="4577" title="Web Browsers" author-id="5884" timestamp="2013-03-14 20:49:27 +0000" type="norm" dbname="box9488" last-modified-by="127" %}
The newest and hottest addition to the Radio PSI experience is the new Browser Player. With this you can listen to Radio PSI right from any modern browser, <i>even on your smartphone or tablet device</i>, and you don't have to download a media player or that pesky Java thing, either!

<p>As a note, this is highly experimental. If you experience issues, please wait 5-10 seconds after clicking the button before clicking Play. It has also been known to start playing and <i>then</i> decide to buffer for 10-20 seconds; this is largely browser dependent.
</p>

<p>If you do experience any problems using this option, please let Cyan683 know in <a href="http://starmen.net/radio/miscellaneous/irc.php">#radiopsi on IRC</a>.
</p>

<br /><input id="browserPlayerButton" type="button" value="Load" onClick="var myFrame=document.getElementById('browserPlayer'); myFrame.src = 'http://icecast.fobby.net/browserplayer/browserPlayer.xsl'; myFrame.hidden=false; document.getElementById('browserPlayerButton').value='Reload';" />

<br />
<br /><iframe id="browserPlayer" src="" style="height:160px; width:445px;" scrolling="false" seamless="true" hidden="true">Your browser does not seem to support frames.</iframe>
{% include box-close.html author-name="cyan683" last-modified-on="2013-03-16 00:49:39 +0000" last-modified-by-name="cyan683" %}

{% include box-open.html box-id="4578" title="Music Players" author-id="5884" timestamp="2013-03-14 20:49:49 +0000" type="norm" dbname="box65341" last-modified-by="127" %}
Many music players are able to play Radio PSI.

<p>To listen using a music player, you can either click on the links we post in news updates and have your browser open it in your music player or you can download <a href="http://starmen.net/radio/radiopsi.m3u">this playlist</a>, save it on your computer, and open it anytime you want to listen (Assuming we're on, of course!). It will tell most players to try each of the addresses so it will always find who's on.
</p>

<ul>
<li><img src="http - //starmen.net/radio/images/icons/vlc.png" /> VLC is known to function correctly.</li>
<li><img src="http - //starmen.net/radio/images/icons/winamp.ico" /> Winamp is known to function correctly.</li>
<li>mplayer is known to function correctly, but version-specific issues have been noted. It is considered supported, but is not guaranteed to be compatible.</li>
</ul>
{% include box-close.html author-name="cyan683" last-modified-on="2013-03-14 20:50:07 +0000" last-modified-by-name="cyan683" %}

{% include box-open.html box-id="4579" title="Java Radio" author-id="5884" timestamp="2013-03-14 20:50:11 +0000" type="norm" dbname="box3325" last-modified-by="127" %}
<div id="java">
Browser not working with the Browser Player? Can't tune in from your Winamp?  Windows Media Player just not cutting it?  Don't <b>feel</b> like downloading other players like Foobar2000 or VLC just to listen in?  All you need is Java! The next time Radio PSI is rocking out, and your preferred media player can't possibly handle the awesomeness, just click the button below to get connected, and enjoy!*

<p>
<div align="center"><popupbutton src="http://icecast.fobby.net/jorbis/index.html" width="450" height="60" value="Launch Java Radio" /></div>
</p>

<p>* If you use Java Radio and see sarsie around on IRC, be sure to thank her for installing this wonderful piece of technology!
</p>
</div>
{% include box-close.html author-name="cyan683" last-modified-on="2013-03-16 18:23:19 +0000" last-modified-by-name="cyan683" %}
