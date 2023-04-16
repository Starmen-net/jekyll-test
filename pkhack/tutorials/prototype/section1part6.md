---
title: Prototype&#039;s PK Hack Tutorial
categories:
  - pkhack
date: 2012-03-11 18:39:22 +0500
---
{% include box-open.html box-id="4347" title="New Box, Edit me :(:" author-id="6189" timestamp="2012-03-11 18:39:22 +0500" type="blank" dbname="box32605" last-modified-by="127" %}
<center><font size="5">1.6 Frequently Asked Questions</font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:46:46 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4348" title="I just downloaded PK Hack and it won't run:" author-id="6189" timestamp="2012-03-11 18:39:46 +0500" type="norm" dbname="box306" last-modified-by="127" %}
You NEED to have the proper version of Java installed on your machine. Depending on your system, you may need to create a batch file that sends the proper command to open the .jar file. If this still doesn’t fix the problem, ask in the Help/Troubleshooting topic.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:40:22 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4349" title="PK Hack runs, but I can only use two of the general tools; the rest don’t work.:" author-id="6189" timestamp="2012-03-11 18:40:28 +0500" type="norm" dbname="box53014" last-modified-by="127" %}
This means your ROM is NOT the proper EarthBound ROM. It might play in an emulator, but it’s still a bad dump. Get the proper ROM with the CRC listed in section 1.4.1. Google if you don’t know how to check the CRC of a ROM. I’m sure you will find the one causing JHack to act odd has a different CRC. This is usually the result of a missing header, which is also explained in 1.4.1. If you are comfortable with hex editing, it’s possible to add the header yourself and fix the ROM. Get a good ROM, and this problem will go away.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:40:52 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4350" title="I start a new game, but Ness is in his PJ’s, there are no enemies, and Onett is dark:" author-id="6189" timestamp="2012-03-11 18:41:02 +0500" type="norm" dbname="box32580" last-modified-by="127" %}
The ROM begins the game in a certain state that was actually programmed into the game, and not done with control codes after the game starts. Certain flags are tripped from the start, and need to be changed to get the game back to what is considered the default state the game will be in for most of the game. The flag for Onett’s palette swap is $1A6 (A6 01). The flag for enemies being in existance is $00B (0B 00). The flag to change Onett back to Daytime music is $068 (68 00). The flag for Ness’s PJ’s is $2ED (ED 02). $177 (77 01) might be related to people being visible in Onett. $205 (05 02) changes the inside of Ness’s house to daytime. $215 (15 02) when on makes sure that the Meteor effect doesn’t happen when entering Ness’s room. There may be a few more flags, check out the opening sequence in the original ROM to make sure.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:41:22 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4351" title="I skipped the opening flyover in my hack, and things broke:" author-id="6189" timestamp="2012-03-11 18:41:35 +0500" type="norm" dbname="box50106" last-modified-by="127" %}
This ties into the previous question. When you skip the flyover, you also skip over a number of flags being set
and such. You need to create your own text that plays at the beginning to allow you to finish “initializing” the game. You don’t have to USE the flyover, but it’s usually easier that figuring out which parts of the code you need to use to get things working properly.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:41:53 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4352" title="Is there any way to give the 3rd character PSI?:" author-id="6189" timestamp="2012-03-11 18:42:04 +0500" type="norm" dbname="box20480" last-modified-by="127" %}
It’s possible, and has been done before, but it’s very difficult to do, and requires some ASM trickery. More
details are in the section for advanced editing of the EarthBound ROM.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:42:15 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4353" title="When I try to enter buildings, the game freezes and an arrow appears in the upper left hand corner of the screen:" author-id="6189" timestamp="2012-03-11 18:42:27 +0500" type="norm" dbname="box31814" last-modified-by="127" %}
There is an error with the text block linked to the door. Change it to null (0), or check the text block again.
Make sure if there is supposed to be text, you are opening a window for the text to appear in.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:42:58 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4354" title="PK Hack crashes with an out of memory error, usually when editing the map:" author-id="6189" timestamp="2012-03-11 18:43:04 +0500" type="norm" dbname="box43621" last-modified-by="127" %}
This is because by default, Java will only use about 64MBs of memory, and then throw up the out of memory exception when it runs out, instead of requesting more. Given the size of the map, it’s easy to get this error when editing the map. The good news is, you can manually change the maximum size of the memory Java has availible to it. In windows, open your command console(run, cmd), and give it the command javaw -xmx(). Instead of (), give it a number followed by m. This is how many megabytes you will let it use. Try bumping it to 256 to see if it solves the problem.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:43:49 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4355" title="X is broken in my ROM, how do I fix it?:" author-id="6189" timestamp="2012-03-11 18:43:55 +0500" type="norm" dbname="box47387" last-modified-by="127" %}
Post about it in the Help/Troubleshooting topic, and we MIGHT be able to help. I say might, since not everything is understood or fixable.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:44:05 +0500" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4356" title="New Box, Edit me :(:" author-id="6189" timestamp="2012-03-11 18:44:08 +0500" type="blank" dbname="box2707" last-modified-by="127" %}
<center><font size="4"><a href="section1part5.php">&larr; 1.5 PK Hack's Tools</a> | <b>1.6 Frequently Asked Questions</b> | <a href="section2.php">2.0 Tileset and Map Editing &rarr;</a></font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 18:46:50 +0500" last-modified-by-name="NESluver" %}
