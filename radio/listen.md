---
title: Radio PSI - How to Listen
categories:
  - radio
date: 2007-06-30 21:42:13 +0000
---
{% include box-open.html box-id="4581" title="The Basics" author-id="5884" timestamp="2013-03-17 17:56:24 +0000" type="norm" dbname="box61882" last-modified-by="127" %}
Unlike standard over-the-air radio and television broadcasts, you can only tune in live when someone is currently broadcasting, so it's useful to <a href="http://starmen.net/radio/schedule.php">consult the schedule</a>, or you can keep an eye on the notification board in <a href="http://starmen.net/radio/discord.php">Radio PSI's Discord Server</a> for notifications that a show or one of the DJs are doing extra content on the side.

There are several ways to listen to Radio PSI, here are the most common.
{% include box-close.html author-name="cyan683" last-modified-on="2023-01-25 03:53:58 +0000" last-modified-by-name="nightshade" %}

{% include box-open.html box-id="5559" title="Twitch" author-id="9233" timestamp="2023-01-25 06:23:40 +0000" type="norm" dbname="box853" last-modified-by="127" %}
<p>
Radio PSI now features video streaming which is now the main broadcasting source for Radio PSI programming. Even show formats designed for audio will be broadcasted to Twitch unless circumstances prevent it.
</p>

<p>
The official Twitch channel for Radio PSI can be found <a href="http://www.twitch.tv/radiopsi">here</a>*.
</p>

<iframe
    src="https://player.twitch.tv/?channel=radiopsi&parent=starmen.net"
    height="300"
    width="400"
    allowfullscreen="true">
</iframe>

<p>
*Due to special circumstances, Radio PSI programmings from DJ AmzTrak are being broadcasted on <a href="http://www.twitch.tv/amzrigh">his personal channel</a>. When this occurs, the Radio PSI Discord chat channel is bridged to this channel's chat to replicate the usual experience between the Radio PSI chat channels.
</p>
{% include box-close.html author-name="nightshade" last-modified-on="2023-04-03 04:04:38 +0000" last-modified-by-name="nightshade" %}

{% include box-open.html box-id="4540" title="Web Browsers" author-id="5884" timestamp="2012-10-09 19:48:11 +0000" type="norm" dbname="box8504" last-modified-by="127" %}
Radio PSI shows that are broadcasted to audio sources can be listened via most Internet browsers' built-in media player. With this, you can listen to Radio PSI right from any modern browser on desktops, mobile devices and tablets without the need to download and install any media player.

<p>As a note, the player will only be available when a broadcast is ongoing. If the player doesn't appear, click the Reload button to attempt again. If you experience issues with the player itself, please wait 5 to 10 seconds after clicking the Listen button before clicking Play. It is browser dependent, but the player is known to start playing and then buffer from 10 to 20 seconds.
</p>

<p>If you do experience any problems using this option, please let Cyan683 know in the <a href="http://starmen.net/radio/miscellaneous/discord.php">Radio PSI Discord Server.</a>.
</p>

<br /><input id="browserPlayerButton" type="button" value="Listen" onClick="var myFrame=document.getElementById('browserPlayer'); myFrame.src = 'http://icecast.fobby.net/browserplayer/browserPlayer.xsl'; myFrame.hidden=false; document.getElementById('browserPlayerButton').value='Reload';" />

<br />
<br /><iframe id="browserPlayer" src="" style="height:160px; width:445px;" scrolling="false" seamless="true" hidden="true">Your browser does not seem to support frames.</iframe>

<span style="font-size:0.75em">Note: Many browsers cause significant lag when listening. Please consider this when participating in radio conversations.</span>
{% include box-close.html author-name="cyan683" last-modified-on="2023-01-25 06:39:07 +0000" last-modified-by-name="nightshade" %}

{% include box-open.html box-id="4541" title="Music Players" author-id="5884" timestamp="2012-10-09 20:07:43 +0000" type="norm" dbname="box32628" last-modified-by="127" %}
<p>
Multiple music players are able to play Radio PSI.
</p>

<p>
To listen using a music player, you can open the URL <a href="http://icecast.fobby.net/radiopsi.ogg.m3u">http://icecast.fobby.net/radiopsi.ogg.m3u</a> and play it when a show is broadcasting via the audio source. You can also set the play on loop so it can attempt to reconnect should it loses connection during the broadcasting.
</p>

<p>
Here is a list of confirmed media players able to play the audio source when being broadcasted:
</p>

<ul>
<li><img src="http://starmen.net/radio/images/icons/vlc.png" /> VLC is known to function correctly. To do so, open a Network Stream (Ctrl+N) and copy the URL.</li>
<li><img src="http://starmen.net/radio/images/icons/winamp.ico" /> Winamp is known to function correctly. To do so, add an URL to the playlist (Ctrl+L) and copy the URL.</li>
</ul>

<p>
Feel free to share with us other media players that you know is able to work with the audio broadcast.
</p>
{% include box-close.html author-name="cyan683" last-modified-on="2023-01-25 06:52:47 +0000" last-modified-by-name="nightshade" %}

{% include box-open.html box-id="3148" title="Java Radio" author-id="247" timestamp="2007-06-30 21:42:13 +0000" type="norm" dbname="box41942" last-modified-by="127" %}
<div id="java">
Should all else fails and there is an audio broadcast currently airing, you might fall back to our legacy Java Player*. As the name implies, you will require to have Java Runtime installed on your computer in order to execute it.

<p>
<div align="center"><popupbutton src="http://icecast.fobby.net/jorbis/index.html" width="450" height="60" value="Play Radio PSI" /></div>
</p>

<p>
* Starmen.net veterans might recognize the name sarsie. She was the person behind the creation of the Java Player that has served Radio PSI for so many years. Though it is now considered a legacy method, we thank her nonetheless for installing this piece of Radio PSI history!
</p>
</div>
{% include box-close.html author-name="Mansion Maniac" last-modified-on="2023-01-25 06:58:16 +0000" last-modified-by-name="nightshade" %}
