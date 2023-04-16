---
title: 'EarthBound Debug Menu #2'
categories:
  - mother2
date: 2007-06-23 00:59:55 +0500
---
{% include box-open.html box-id="3085" title="EarthBound Debug Menu #2:" author-id="288" timestamp="2007-06-23 00:59:55 +0500" type="norm" dbname="box52917" last-modified-by="127" %}
<center><img src="debugmenu2.png" /></center>

<br />
This second debug menu in EarthBound has actually been known about <a href="http://hijola.starmen.net/articles/debug.html">for a very long time</a>. We just never had any idea how to access it or what exactly it did. But then thanks to Cabbage, <a href="http://oldforum.starmen.net/cgi-bin/ultimatebb.cgi?ubb=get_topic;f=8;t=000350">we finally got access to it</a> in early 2003.

<br /><br />
This debug menu looks like it was used by a team at HAL (hence the Kirby sprite) that worked a lot on the map and walking around part of the programming. The other debug menu seems like it was meant for people testing the text, the text parsing system, events, and other things that are handled by the game's text.
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 01:31:12 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3086" title="Accessing the Debug Menu:" author-id="288" timestamp="2007-06-23 01:22:26 +0500" type="norm" dbname="box52533" last-modified-by="127" %}
<font color="red"><b>Caution! This debug menu is (ironically) extremely buggy! Use caution!</b></font>

<br /><br />
The easiest way to access this debug menu is with three Game Genie codes:<br /><br />

<center><font size="4"><b>6B88-54D4<br /><br />3188-5404<br /><br />3E88-5464</b></font></center>

<br />
Or, if you're more technically inclined, use a hex editor, go to address BBB8, and change the bytes "<b>D8 B7 C0</b>" to "<b>89 E6 EF</b>".

<br /><br />
Once you've done one of these two things, start up the game!
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 14:57:17 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3087" title="Controls:" author-id="288" timestamp="2007-06-23 01:39:54 +0500" type="norm" dbname="box2317" last-modified-by="127" %}
The different controls for various parts of the debug menu are:

<ul>
 <li> <b>A</b> – Turns the screen black for a second. The Ness image is placed wherever you moved the invisible sprite.</li>

 <br /><br />
 <li><b>B</b> – Brings up the Talk menu, etc., as it would in the game. Do whatever you want, but as soon as you exit it, the game will freeze. If you go right in front of someone with your aiming correct and press B to bring up the menu, and then press A to talk to them, it will bring up their text, but the game will freeze afterward.</li>

 <br /><br />
 <li><b>Y</b> – This is the most interesting part of the "View Map" option. It pulls up a special menu, which is described in great detail below.</li>

 <br /><br />
 <li><b>X</b> – Nothing</li>

 <br /><br />
 <li><b>L</b> – Nothing</li>

 <br /><br />
 <li><b>R</b> – Nothing</li>
</ul>
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 01:47:01 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3088" title="GAME:" author-id="288" timestamp="2007-06-23 01:50:55 +0500" type="norm" dbname="box13161" last-modified-by="127" %}
Selecting the "Game" option on the debug menu will begin the game like normal. So this is sort of like the "exit the debug menu" option.
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 01:52:13 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3089" title="VIEW MAP:" author-id="288" timestamp="2007-06-23 01:52:26 +0500" type="norm" dbname="box18825" last-modified-by="127" %}
<ul class="pics">
<li>
<a class="picleft"><img src="debug2_page1.png" align="center" /></a>
<h3>PAGE #1</h3>
<p><b>Flag</b> - Controls what event flags are turned on and off.</p>
<p><b>Goods</b> - Gives you any items you want. Consult PK Hack for a list.</p>
<p><b>Save</b> - Saves your game and whatever you've done here.</p>
<p><b>Apple</b> - Brings up the other debug menu.</p>
<p><b>Banana</b> - Switches from View Map mode to Game mode.</p>
<p><b>tx6</b> - Takes you to the next page of the menu.</p>
<div class="hr"><hr /></div>
</li>

<li>
<a class="picleft"><img src="debug2_page2.png" align="center" /></a>
<h3>PAGE #2</h3>
<p><b>TV</b> - Unknown. Usually leads to the game freezing.</p>
<p><b>Event</b> - Unknown. Is buggy for now.</p>
<p><b>Warp</b> - Warps you to the Happy Happy headquarters. Buggy.</p>
<p><b>Tea</b> - Lets you watch the tea scene.</p>
<p><b>6?K –</b> - Leads back to Page #1.</p>
<div class="hr"><hr /></div>
</li>

<li>
<a class="picleft"><img src="debug2_page3.png" align="center" /></a>
<h3>PAGE #3</h3>
<p><b>+?u456789:;&lt;=&gt;?*ABCEDFGHIJKu|| || || || | !". –</b> - Leads back to Page #1.</p>
<p><b>GUIDE  )**,-./012345 –</b> - Shows the town maps. Press down to cycle through them.</p>
<div class="hr"><hr /></div>
</li>

<li>
<a class="picleft"><img src="debug2_page4.png" align="center" /></a>
<h3>PAGE #4</h3>
<p><b>CAST</b> - Unknown. Acts strange, but so far does nothing.</p>
<p><b>STONE</b> - Shows the cast of characters. No music, and freezes when done.</p>
<p><b>STAFF</b> - Displays the Sound Stone screen. Doesn't freeze afterward!</p>
<p><b>"ue' ()**,-./0123456789:;&lt;=&gt;</b> – Rolls the staff credits.</p>
<div class="hr"><hr /></div>
</li>

<li>
<a class="picleft"><img src="debug2_page5.png" align="center" /></a>
<h3>PAGE #5</h3>
<p><b>REPLAY</b> - Unknown. Exits menu and freezes.</p>
<p><b>TEST 1</b> - Unknown. Goes through Paula's prayer text.</p>
<p><b>TEST 2</b> - Causes some very strange stuff. Try it at least once!</p>
<div class="hr"><hr /></div>
</li>

</ul>
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 02:40:30 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3090" title="VIEW CHARACTER:" author-id="288" timestamp="2007-06-23 02:43:45 +0500" type="norm" dbname="box23921" last-modified-by="127" %}
<ul class="pics">
<li>
<a class="picleft"><img src="coordinates.png" align="center" /></a>
<p>Even though it may sound like you can change a bunch of stuff with the characters here, you really can't. It's about the same as View Map, but with one difference: you can see the character's game coordinates. As you move along, the little numbers change. That's all.
<br /><br />
Also, the keys are the exact same as in View Map, but this time the menu options are inside a clear menu.</p>
<div class="hr"><hr /></div>
</li>
</ul>
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 02:48:44 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3091" title="VIEW ATTRIBUTE:" author-id="288" timestamp="2007-06-23 02:49:46 +0500" type="norm" dbname="box51366" last-modified-by="127" %}
<ul class="pics">
<li>
<a class="picleft"><img src="attribute.png" align="center" /></a>
<p>This one is like an exact clone of the View Map Mode one, except, this time, the menu is transparent.</p>
<div class="hr"><hr /></div>
</li>
</ul>
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 02:51:16 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3092" title="SHOW BATTLE:" author-id="288" timestamp="2007-06-23 02:51:45 +0500" type="norm" dbname="box369" last-modified-by="127" %}
No info.
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 02:51:54 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3093" title="SHOW POSITION:" author-id="288" timestamp="2007-06-23 02:51:58 +0500" type="norm" dbname="box20293" last-modified-by="127" %}
<ul class="pics">
<li>
<a class="picleft"><img src="position.png" align="center" /></a>
<p>Like View Map, but this time you see all sorts of coordinate data. Testers and developers used this to fine-tune position-based events and the like.</p>
<div class="hr"><hr /></div>
</li>
</ul>
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 02:53:47 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3094" title="SOUND MODE:" author-id="288" timestamp="2007-06-23 02:58:02 +0500" type="norm" dbname="box65360" last-modified-by="127" %}
<ul class="pics">
<li>
<a class="picleft"><img src="soundmode.png" align="center" /></a>
<p>Lets you listen to any music, sound effect, or music effect in the game. A list of music and sound effects can be found <a href="/pkhack/pk_docs/muzak.txt">here</a>.</p>
<div class="hr"><hr /></div>
</li>
</ul>
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 02:59:58 +0500" last-modified-by-name="Tomato" %}

{% include box-open.html box-id="3095" title="Thanks To:" author-id="288" timestamp="2007-06-23 03:00:45 +0500" type="norm" dbname="box59296" last-modified-by="127" %}
Thanks go to Cabbage for figuring out how to access this debug menu, NLA for compiling most of this information, and the PK Hack community for being cool and helpful.
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-23 03:01:43 +0500" last-modified-by-name="Tomato" %}
