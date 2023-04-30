---
title: Prototype&#039;s PK Hack Tutorial
categories:
  - pkhack
date: 2012-02-10 17:28:58 +0000
---
{% include box-open.html box-id="4245" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-10 17:28:58 +0000" type="blank" dbname="box45278" last-modified-by="127" %}
<center><font size="5">1.3 Editing Order</font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:34:07 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4246" title="Step 1: Mapping and Tilesets" author-id="6189" timestamp="2012-02-10 17:30:04 +0000" type="norm" dbname="box81" last-modified-by="127" %}
Do this absolutely first. The majority of crashes, glitches, and ruined ROMs happens when editing Tilesets and
the Map. There is no sense in putting any work into the ROM before getting this done. It helps to create some script
for starting somewhere without enemies turned on to test your map before moving on.

<br /><br />

IMPORTANT! When expanding your ROM to 4MBs to fit in new stuff so you can edit safely, use Mr. Accident’s Map Editor, not JHack. Use JHack AFTER you’ve expanded with Mr. A’s if you need to make it 6MBs(LARGE hacks, tons of text) and only AFTER you’ve finished making your map. Mr. Accident’s map editor can ONLY use 4MB files, and expanding them in JHack tends to cause issues for Mr A’s editor. For most hacks, use Mr. A’s editor to expand the ROM if you plan on doing ANY map editing.
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 22:03:55 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4247" title="Step 2: Enemy Group Editing" author-id="6189" timestamp="2012-02-10 17:30:49 +0000" type="norm" dbname="box13020" last-modified-by="127" %}
This is confusing, and very difficult to do, we are also not 100% on how it functions.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:31:06 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4248" title="Step 3: ASM" author-id="6189" timestamp="2012-02-10 17:31:07 +0000" type="norm" dbname="box6150" last-modified-by="127" %}
Do all ASM work now, if you are doing any. If not, skip this step.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:31:23 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4249" title="Step 4: Sprite Editing and Font Editing" author-id="6189" timestamp="2012-02-10 17:31:27 +0000" type="norm" dbname="box19418" last-modified-by="127" %}
Finish the rest of the graphical work now. If you are done with this step and your ROM is still stable and
working, you might finish your ROM. It’s downhill from here.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:31:47 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4250" title="Step 5: Misc Editing" author-id="6189" timestamp="2012-02-10 17:31:50 +0000" type="norm" dbname="box12600" last-modified-by="127" %}
Changing the coffee sequences? Flyovers? Intro? Stats? Items? Enemies? Anything else that isn’t just
editing text can be done now. Now would be a good time to edit the music and check it out in-game. Once you are done,
you will have all the parts in place, and just need to do all the writing and link everything together. This is the
end of the Alpha stage.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:32:16 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4251" title="Step 6: Text Editing and Scripting" author-id="6189" timestamp="2012-02-10 17:32:19 +0000" type="norm" dbname="box61164" last-modified-by="127" %}
Every line of dialogue, every action an enemy takes, choices you can make, and anything else you can code
together will be made now. You will make all the scripts that link all the text to the sprites and SPT and TPT entries.
This should be the last step to finishing your hack, and is where you enter the final beta stages. To make things
easy on yourself, you can do this part in sequence to how it should play out in game. This is when you will be doing
most of your beta testing and asking others to test in order to find errors and bugs.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:32:47 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4252" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-10 17:32:53 +0000" type="blank" dbname="box7669" last-modified-by="127" %}
<center><font size="4"><a href="section1part2.php">&larr; 1.2 Websites and locations of other info</a> | <b>1.3 Editing Order</b> | <a href="section1part4.php">1.4 Technical Details &rarr;</a></font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-10 17:34:44 +0000" last-modified-by-name="NESluver" %}
