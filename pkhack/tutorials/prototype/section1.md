---
title: Prototype&#039;s PK Hack Tutorial
categories:
  - pkhack
date: 2012-02-10 16:12:29 +0000
---
{% include box-open.html box-id="4214" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-10 16:12:29 +0000" type="blank" dbname="box25201" last-modified-by="127" %}
<center><font size="5">1.0 General Rules and Concepts</font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:12:31 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4215" title="Rule #1" author-id="6189" timestamp="2012-02-10 16:15:04 +0000" type="norm" dbname="box7309" last-modified-by="127" %}
<center><img src="http://www.starmen.net/pkhack/tutorials/prototype/images/backups.png" /><br /><br /></center>

Keep multiple backups of the original ROM, as well as the ROM you are working on. I’d go so far
as to recommend you keep a history of ROM backups, so it’s easier to pinpoint what went wrong (and when) when your ROM gets glitched out. JHack is notorious for destroying ROMs and ruining hours, days, months, and even years of effort. Don’t let it happen to you. Be smart, keep copies and backups. I have copies of my copies on multiple PC’s. Don’t say I didn’t warn you.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 16:21:10 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4216" title="Rule #2" author-id="6189" timestamp="2012-02-10 16:21:11 +0000" type="norm" dbname="box56609" last-modified-by="127" %}
<center><img src="http://www.starmen.net/pkhack/tutorials/prototype/images/freespace.jpg" /><br /><br /></center>

The original ROM is only 3MB’s, and tightly packed, you can’t really ADD things without expanding.
Any change you make that is larger than what was there in the first place will most likely overwrite the section after it, and this can either cause minor fixable problems, or completely break a ROM. As a general rule, if you plan on ADDING anything, you MUST expand your ROM, and put the new stuff in the expanded area. Doing this is explained later, just keep the rule in mind.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-20 23:59:00 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4217" title="Rule #3" author-id="6189" timestamp="2012-02-10 16:23:48 +0000" type="norm" dbname="box27952" last-modified-by="127" %}
<center><img src="http://www.starmen.net/pkhack/tutorials/prototype/images/writeitdown.png" /><br /><br /></center>

Know what you are doing BEFORE you start hacking. I don’t mean fully understand every little detail
beforehand, I mean have a VERY clear idea of what you want. Before you even open JHack, sit down with a pencil and paper,
or use Paint and Notepad, and map out what you are trying to do. Given the 80 million variables JHack can throw at you,
if you don’t know exactly what you want to do, it’s easy to get swamped. Also when hacking it helps alot to know what is
a core component of your hack, and what is just something you thought would be nice to do, and which can be cut if need be.
So map it out. What changes do you plan on making? Are you changing existing areas, deleting some and making a few new
areas? Are you changing enemies? Items? Getting it all out on paper will help you remember everything you wanted to do, instead of trying to keep everything in your head. Starting a hack with just a general idea of what you are going to dois a good recipe for disaster. This goes double when dealing with the Map, as you will find out later.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 16:27:31 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4218" title="Rule #4" author-id="6189" timestamp="2012-02-10 16:29:49 +0000" type="norm" dbname="box5835" last-modified-by="127" %}
<center><img src="http://www.starmen.net/pkhack/tutorials/prototype/images/ebshoptext.jpg" /><br /><br /></center>

EarthBound was made by people who must have been on drugs. The ROM is one of the most disorganized and
messy pieces of code in existance. The above picture is of the code used by the game for the Stores. It’s a giant
“If X is Y, do A, else do B” tree that uses the flags in the EarthBound system to determine which store you are at.
Rather than just have a seperate block of code for each store like would be logical, instead every single time you
talk to one of the NPC’s with a store in game, the game calls this piece of code and runs down the tree until it finds the
store you are at based on which flags are set and which ones are not. This means editing any store in the game is a
MASSIVE hassle. Not a whole lot you can do about this, unless you put alot of work into it. This is just a small sample
of how messed up the ROM is. This isn’t simple. We don’t know how to edit everything, what everything is or does,
or why some completely unrelated things have a tendacy to effect one another. That’s just the way the ROM is.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-20 23:57:12 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4219" title="Rule #5" author-id="6189" timestamp="2012-02-10 16:35:30 +0000" type="norm" dbname="box60436" last-modified-by="127" %}
<center><img src="http://www.starmen.net/pkhack/tutorials/prototype/images/disassembled.png" /><br /><br /></center>
Understand the components. The ROM has sections of itself that are Audio data, Graphical data, Assembly,
plain text, Compressed text, Compressed Graphical data, an internal control code system, and some stuff we haven’t ID’d yet.
These parts aren’t always contigious either. The Audio data alone is scattered all over the ROM in 15 different areas.
Different parts of the game are stored in various ways across the ROM. Knowing where the data you want to edit is,
and how to access it and alter it are key to hacking. This ties in with Rule #8.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 16:37:54 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4220" title="Rule #6" author-id="6189" timestamp="2012-02-10 16:39:51 +0000" type="norm" dbname="box49953" last-modified-by="127" %}
<center><img src="http://starmen.net/pkhack/tutorials/prototype/images/hex.png" /></center><br /><br />Know the terms and concepts. Do you understand the concept of Hexadecimal? Do you know what a pointer
is in the context of programs and memory? Are you familiar with the concept of binary flags? Do you understand the flow-
chart of a program? Do you know what an argument is in context to programming? Do you know how the EarthBound ROM stores
pointers, and how to convert them to a hex pointer you can follow? Do you understand the programming concept of a IF/ELSE
statement? Do you know what a color palette is? If you answer no to any of these questions, don’t worry, I will explain
these things in section 1.4.0 Technical Details.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-20 23:54:39 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4221" title="Rule #7" author-id="6189" timestamp="2012-02-10 16:40:07 +0000" type="norm" dbname="box53595" last-modified-by="127" %}
Many things you may want to do are possible with the simple editing of a value in one of JHack’s editors,
or the built-in Hex editor, but some things require ASM to alter. Granted, Graphical and Audio data require their own
editors, but most other editable things fall into this catagory. Editing a spell to cost more PP is simple, since that
value is stored in plain text in a table somewhere. Editing a spell to do different damage is very complicated, since
that data is in Assembly, and requires knowledge of 65816 Assembly code to change, and Assembly requires knowledge of
the hardware of the SNES, and nifty things like memory registers.(I do not know Assembly, this is not a 65816 Assembly
tutorial, google if you want one) So you can do many things quite easily, but some things are very difficult to do, and
require learning far more than this tutoral is for. This ties in with Rule #8.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 16:42:00 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4222" title="Rule #8" author-id="6189" timestamp="2012-02-10 16:40:21 +0000" type="norm" dbname="box18768" last-modified-by="127" %}
<center><img src="http://www.starmen.net/pkhack/tutorials/prototype/images/tool.png" /><br /><br /></center>
Know the tools needed for the job. As a simple rule, if it involves editing Audio or sound effects,
EBMused, PKMidi, and a different tutorial is what you need. If it involves editing graphical data of any kind, you will
be using one of the built-in editors in JHack, or using the Reset Button in JHack to decompress the data(if needed), and
editing with Tile Layer Pro, Tile Molester, or your other favorite SNES graphical editing program. If it involves text,
most work should be done with CCScript, and put into the expanded area. If it involves editing a function of how the game
operates, odds are you will need to do the work in Assembly, and as I’ve said before, I can’t help you there.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 16:44:10 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4223" title="Rule #9" author-id="6189" timestamp="2012-02-10 16:40:23 +0000" type="norm" dbname="box49087" last-modified-by="127" %}
<center><img src="http://www.starmen.net/pkhack/tutorials/prototype/images/badluck.png" /><br /><br /></center>
You can do everything right and still be not able to finish. JHack eats ROMs, and sometimes things
break and we don’t know why, or how to fix them. Like I’ve said, many parts of the EarthBound ROM are unknown, and we
don’t fully understand the ROM. Messianic created EB:DX, a super hard edition hack of Earthbound. He put tons of effort,
time, and work into his hack, and it now sits near completion due to a number of bugs we just can’t seem to get rid of.
Hacks do get done, but there is always that chance. Better you know now before you get started.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 16:49:08 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4224" title="Rule #10" author-id="6189" timestamp="2012-02-10 16:40:25 +0000" type="norm" dbname="box40762" last-modified-by="127" %}
<center><img src="http://starmen.net/pkhack/images/frontpage/hotm/hotm012012tmm.png" /><br /><br /></center>
Hacking takes time and effort, completing a hack takes time, effort, persiverance, and a bit of luck.
There is no way you will accomplish anything in editing the EarthBound ROM if you are not willing to put effort into it.
Trial and error, breaking the ROM with editing, examining how the game does things and trying to emulate that, this all
requires a desire to learn and to put in the time needed to hack. It’s not easy, and results don’t come quickly. The
ROM itself is also a mess making things even harder to work with. If you tend to start projects and not finish them,
this may not be for you. No one is really looking for an idea guy for a project, or a project leader. There may be
people willing to help with a part of a hack, but we don’t want to do your hacking for you. As such, we expect you to
put in effort, like reading the Forum Rules before posting.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 16:51:21 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4225" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-10 16:52:41 +0000" type="blank" dbname="box43737" last-modified-by="127" %}
<center><font size="4"><a href="section0.php">&larr; Preamble</a> | <b>1.0 General Rules and Concepts</b> | <a href="section1part1.php">1.1 Programs &rarr;</a></font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:12:23 +0000" last-modified-by-name="NESluver" %}
