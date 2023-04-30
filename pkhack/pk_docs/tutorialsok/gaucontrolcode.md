---
title: Sweet, Sweet, Control Code Love
categories:
  - pkhack
date: 2006-08-23 20:14:34 +0000
---
{% include box-open.html box-id="2543" title="This is the entire tutorial" author-id="473" timestamp="2006-08-23 20:14:34 +0000" type="norm" dbname="box7501" last-modified-by="127" %}
<font size="3"><b>Your First Hack</b></font><br />
<i>By Gau</i><br /><br />


Ah, text editing. A joy and a curse all at once.<br />

I think, first of all, if you're going to be editing text (which is a major point for many hackers) you should know a little bit more than the average Joe ABOUT text editing. For, as you will see, when we say 'text editing', we really mean the hacking of anything inside the text block. In this text block, there are three different types of data. The first is plain text (in hexadecimal of course.) The second are what we call 'control codes'. <br /><br />

 - Control Code (noun). Any hexadecimal code, appearing in the text block, that activates an event, sound, movement, action, or the like. <br /><br />

The third and final type is compressed text. You see, because of the size limitations of the SNES cartridge, the programmers of Earthbound decided to compress a great deal of the data in Earthbound to save space. Fortunately for us, not only do we have the option of adding an additional megabyte of space to the ROM, but we also have the option of compressing our own text. This will allow us to prevent overwrites in our hack. <br /><br />

 - Overwrite 1. (noun) Part of a text block that has extended into the following text block, often destroying the readability and/or usefulness of several adjacent text blocks in the process. <br />
             2. (verb) The act of causing extension into adjacent text blocks. <br /><br />
 

Generally, Overwriting will render your ROM useless, so if you are not working in the Expanded Meg, it's probably a good idea to keep the 'Prevent Overwrites' box in the Text Editor CHECKED. <br /><br />

<b>'Hi Mom!'</b> or, <b>'When are we actually gonna hack something?'</b><br /><br />

One of the dreams of any new hacker is to actually see results from their work. To this end, let's start by opening up the Earthbound Text Editor. (It would actually probably be easier to use the JHack text editor, so you'll probably want to use that instead.) <br /><br />
 
 *!* A note about the Earthbound Text Editor (EBTE): The Earthbound Text Editor, version 3.7, has a flaw regarding the opening of the expanded meg that results in extremely slow load times (anywhere between 30 seconds and 15 minutes.) For this reason, it is recommended that unless you have a top of the line computer, you use the EBTE version 3.0 for editing the Expanded Meg. <br /><br />

So, launch your EBTE, open your ROM, and find this line
@Spit spit spit[10 0F 00]  Saliva spit spit[10 0F 00]  Do you want some gum?[03 00]@Get yer own,[10 0F] twit.[13 02] <br /><br />

An average line, from one of the Sharks in the Onett arcade. Now, see the hexadecimal numbers in brackets? Those are control codes. Though we'll be deleting this line, I think it's a good opportunity to introduce them. <br /><br />

[10 0F 00] This actually has two parts. The [10 0F] part is the pause in the text. The [0F] can be changed to shorten or lengthen the pause. [00] Goes to the next line. It's like pressing Enter in a word processor. <br /><br />

[03 00] Again, this has two parts. The [03] waits for the user to advance the text, while showing the small blinking triangle. Obviously, you know what [00] does. <br /><br />

[13 02] Again, this has two parts. The [13] Is just like [03], it waits for the user to advance the text, only without showing the small blinking triangle. Without this, the text window will automatically close at the end of the text. <br /><br />

[02] Probably the most important control code we're dealing with right now. [02] marks the end of a text block. If you don't add an [02] at the end of your block, the text will continue into the next block. So always put it at the end of every text block, ok? [02] <br /><br />

Now, see the 'at' signs at the beginning of each line? In Earthbound, those are interpreted as the bullets at the beginning of each line. Now that we know what everything in the line does, let's see about creating our own. <br /><br />

@This arcade doesn't have a Dance Dance Revolution machine. [13 02] <br /><br />

Now, notice the 'Current Size' indicator at the bottom. Since we're currently preventing overwrites, the size of the text block MUST be less than 65 bytes. The line above, as you'll see if you paste it in, is 62 bytes. <br /><br />
The next step is to click the 'apply changes' button at the bottom. Now, when you go to talk to this shark in the Arcade, he should say: ·This arcade doesn't have a Dance Dance Revolution machine. <br /><br />

<b>'Wide Open Spaces'</b> or <b>'Text Editing in the Expanded Meg'</b>. <br /><br />

To USE the Expanded Meg, first our ROM has to HAVE an Expanded Meg. (If you are using JHack, which you probably should be using, you're probably already expanded.) So, in the 'Tools' menu of the EBTE, Simply click 'expand'. You should get a message saying your ROM has been expanded. Now, in the options menu, select 'Expanded ROM listing'. It'll take a second or two to load, and then you'll see...a lot of nothing. Click in the upper left-hand corner of the upper window, and in the lower window you should see a lot of 00's. Delete these, and add in your custom message: <br /><br />

@This arcade doesn't have a Dance Dance Revolution machine. [03 00] @How am I supposed to get my groove on? [13 02] <br /><br />

Now, after we've clicked 'Apply Changes', go to the Tools menu, and select View current details. You'll see that the SNES address is $F00000. Now, go back to the Pointer table listing and find the old line. In the Tools menu, select 'Edit TPT entry' and, in the 'SNES Address pointed to', type F00000. Voila, your text should be displayed as typed.
{% include box-close.html author-name="Radiation" last-modified-on="2006-08-23 20:23:04 +0000" last-modified-by-name="Radiation" %}

{% include box-open.html box-id="2544" title="generic box!" author-id="473" timestamp="2006-08-23 20:15:24 +0000" type="norm" dbname="box62894" last-modified-by="127" %}
Okay, that was a pretty sweet tutorial. Click <a href="http://starmen.net/pkhack/documentation.php">here</a> to be brought back. Click <a href="http://pkhack.fobby.net/misc/txt/lexicon.txt">here</a> to be brought to the latest control code listings, since you're a big boy now.
{% include box-close.html author-name="Radiation" last-modified-on="2006-08-23 20:20:49 +0000" last-modified-by-name="Radiation" %}
