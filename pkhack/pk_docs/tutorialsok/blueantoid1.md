---
title: Awesome old-school tutorial
categories:
  - pkhack
date: 2006-09-30 21:29:32 +0500
---
{% include box-open.html box-id="2585" title="How to actually do stuff:" author-id="473" timestamp="2006-09-30 21:29:32 +0500" type="norm" dbname="box58858" last-modified-by="127" %}
<b>Video Game Storywriting 101</b><br />
<i>by Blue Antoid</i><br />
<p />
So, you think you're ready to begin.  You still have much to learn, young one...  but a journey of one thousand miles begins with a single step.  Let us begin.
<p />

<b>- Life, the Universe, and Everything</b><br />
<p />
Look at an EarthBound ROM, and the entire game world lays before you.  People, places, monsters, everything you can imagine.  As a hacker, you can weave all of these disparate objects together to create new worlds for a player to enter and explore.  But if the game has no meaning, would anybody want to explore it?  In a moment, you will learn how to give that vital meaning to your game...
<p />
<b>- A Matter of Scope</b><br />
<p />
I'm going to stop you for a second here...  I have to tell you something.  You may not want to hear it, but...
<p />
<b><center>YOU ARE (MOST LIKELY) <u>NOT</u> GOING TO BE CREATING A 60-HOUR GAME!</center></b>
<p />
Many people assume that to make a hack, they have to change things throughout the entirety of EarthBound.  With our current knowledge of the game, it's completely needless.  On top of that, such a project - assuming you <i>don't</i> take advantage of any new knowledge like graphics compression or map editing - will take over a year.  Believe me, I speak from experience.

<p />
I suppose, at this point, you must feel a bit like Alice...  tumbling down the rabbit hole, hm?  In the coming tutorials you will learn to design a nice, pleasant hack that...  one that somebody may actually enjoy.  Are you ready?  All right, let's get our hands dirty.
<p />
<b>- There's More Than One Way To Skin A Cat</b><br />
<p />
The possibilities are wide open when it comes to creating a hack.  You can modify as much or as little as you wish - the important thing is doing it well.  Here are a handful of categories which make up a good portion of what you can accomplish.
<p />
<i>* Experimental Hacks</i><br />
These aren't really hacks in the normal sense, but I'm going to throw them in for good measure.  An experimental hack will show off what can be done with a particular block of data, to illustrate the meanings and effects of various systems within the ROM, and so forth.  If you ever manage to pull off something really cool, you can wrap it up in a nice little patch and gloat about it to the rest of the community.
<p />
<i>* Cosmetic Hacks</i><br />
Cosmetic hacks are probably the easiest to do.  They are much like what was seen in the early days of PK Hackery, when the only editor we had was the community's namesake.  Ignoring the plot, text, maps, and all other such concerns, a cosmetic hack will deal with what are considered some of the more superficial aspects of hacking - enemy and item names, appearances, and effects, for example.  They can be completely weird and random, or they can be crafted with a specific theme in mind - it's really up to you.  You should try your hand at several cosmetic hacking sessions before making an attempt at a larger, more complex hack.  You'll be surprised how far some concentrated effort in the beginning will go in terms of your later abilities.  Keep these around - as your ability grows, they may snowball into one of the following forms.
<p />
<i>* Easy/Hardtype Hacks</i><br />

A hack such as this entails modifications in the game's difficulty.  Cosmetic concerns are almost completely ignored.  The sorts of things you might edit are enemy stats, strength, and attacks, item drop frequency and prices, <i>et cetera</i>.  If you're feeling adventurous, you may even want to go as far as hacking things like enemy appearance frequencies, level up experience requirements, PSI learning levels and PP costs, main character statistic growth data, and so forth.  This type of hack requires some serious thinking and lots of play-testing.  Above all, gameplay should be balanced, so it is neither too easy nor too hard to be enjoyable.
<p />
<i>* Story Hacks</i><br />
A story hack is just a cosmetic hack taken to the next level - text editing.  The average story hack won't take things very far beyond the preexisting bounds of the game, and only changes the text on a superficial level.  Don't get me wrong - this is by no means simple.  When working within the bounds of the story, you have to find ways to be creative with what's already there.  Instead of a meteor, what else could have crashed on the hill?  Why is the local arcade swarming with enemies?  Why does your hero have to go on a quest at all?  Learning to deal with those situations You'll also face hurdles with respect to 
control codes and event flags - learning what you can get rid of without frelling up the plot, as well as an eventual grasp of pointers, are often key to the success of a story hack.  Such a hack is also a great learning experience, and can be a major stepping stone to bigger and better things.  A good knowledge of EB itself and a strategy guide are big assets when making such a hack.
<p />
I know there are many of you out there who won't be satisfied with this EB hack form, and I don't blame you for feeling that way.  Who could resist the siren song of map editors, advanced control codes, compressed graphics, and the other myriad things we understand today?  Aren't hacks without them overly amateurish and simplistic?  Just remember one thing:  <u>JonBound: Dark Future</u> is a story hack, pure and simple.  It just goes to show that as long as you do it well, you don't have to be on  the cutting edge for people to enjoy and praise your hacking.
<p />
<i>* Tacoriffic Hack Supreme</i><br />
Despite the funky name, this is the goal of most hackers:  to create a masterpiece that goes beyond the bounds of EarthBound itself.  To do so, you'll have to muster all the skills you possibly can.  Not many of these have been created - possibly the best example at the time of this writing is EB_Girl's "Mother 2.5 - The Giftman Chronicles."  They don't have to be very long...  in fact, the longer they are, the HARDER they are.  So don't expect to make one that lasts 60 hours.  Don't even THINK it.
<p />

<i>* So, what the hell?  How could ANYBODY do this?</i><br />
Your best bet, if you intend to make a really serious hack at some point, is to hack, hack, hack, a thousand times hack.  Make cosmetic hacks, story hacks...  just play around as much as you can.  Hacking ability isn't something like being tall...  it's something you build up over time.  And the only way to get it is through constant effort.  Most of the time, you won't even know that you're learning - just be diligent with your hacking efforts, seek out knowledge, and above all have fun... before you know it, you'll be slicing up bytes like a pro.
<p />
<b>- Get On With It!</b><br />
<p />
Okay, I suppose it's time to actually talk about the topic of this tutorial:  Video Game Storywriting.  In this and some future tutorials, I'll be detailing the creation of a short hack of my own - though don't be surprised if the hack comes out before all of the tutorials.  ;)
<p />
<i>* In The Beginning...</i><br />
First thing you're going to have to do is figure out what your hack is going to be about.  I'm going to tell you my process for designing the plot - it's not for everyone, but I think it works pretty well.  One way I use to figure out the plot is to answer the basic questions of journalism - Who, What, Where, Why, and How.  You'll note I left out "When," but unless you're doing some crazy time travel stuff, it's not something you'll be likely to worry about.  :P  As these tutorials go on, I'm going to flesh out a concept story for a hack.
<p />
•<u>Who</u> are your characters - and their friends and enemies, for that matter.<br />

•<u>What</u> are the characters doing?  What is the nature of their adventure?<br />
•<u>Where</u> is all of this happening?  If the game takes place in the EB world, this is possibly the easiest part.  :)<br />
•<u>Why</u> is this happening?  What's the force or motivation behind the quest?<br />
•<u>How</u> do they deal with this?  

<p />
Now, the best way is probably not to treat this like a checklist - this isn't a sort of fill-in-the-blank-thing.  Just imagine the plot of your game - usually dilemma first.  Once an idea springs into your head, start asking those questions.
<p />
"Lucky of the Runaway Five gets kidnapped by insane hippies."  How's that as a dilemma for you?  A bit simplistic right now, but we could work it up into something pretty decent.  The "who" part is almost completely done for us now - our characters are the Runaway Five, and our enemies are the insane hippies.  Easy.  What and Why are also similarly taken care of - the remaining four have to rescue their captured comrade.  How about the other stuff?  Where does this happen?  How about in Twoson area - there are many crazy hippies around there, plus there's an abandoned shack out in the wilderness we could use.  How do they get him back?  Simple detective work - search around town, look for clues as to where Lucky might be, and eventually go and find him.
<p />
See, this is the sort of process that I use to design my plots.  At this stage, it's in very rough, broad strokes...  but as things go on, the ideas will become more and more refined.
<p />
<i>* Story Framework</i><br />
Now that we've constructed a solid foundation upon which to build our hack, we can begin fleshing things out.  When I design a plot, I like to do it in terms of game chapters.  It's a system I devised based on the divisions within the EB Player's Guide.  A simple hack should really be only one or two chapters long.
<p />
A game chapter is defined as a span of the game which encompasses between 10 and 20 different, major events.  It will typically contain two or three major areas to explore, two or three boss battles, and two or three key items used to allow the plot to progress.  Here's a chapter in EarthBound, laid out in this format:
<p /><hr /><p />
Deep Darkness Chapter:<br />
•Areas:  Deep Darkness, Stonehenge Base, Tenda Village/Lumine Hole<br />

•Bosses:  Master Barf, Starman DX, Electro Specter<br />
•Key Items:  Hawk Eye, Eraser Eraser, Shyness Book<p />
Events:<br />
1)  Use the Hawk Eye and traverse Deep Darkness.<br />
2)  Defeat Master Barf and meet Poo again.<br />
3)  Visit Tenda Village.<br />
4)  Get a call from Apple Kid.<br />
5)  Teleport to Dr. Andonuts' Lab.<br />
6)  Get the Eraser Eraser from the mouse.<br />

7)  Explore the depths of Stonehenge Base.<br />
8)  Defeat Starman Deluxe and free the abductees.<br />
9)  Go to the Onett Library and get the Shyness Book.<br />
10) Go back to Tenda Village and give the book to the chief.<br />
11) Talk to the strong Tenda and open the way to Lumine Hole.<br />
12) Explore Lumine Hole Cave.<br />
13) Defeat Electro Specter and get the Seventh Melody.<br />
14) Jump into the hole and go to the Lost Underworld.
<p /><hr /><p />
See?  Nothing to it.  Just take the plot you've created and begin filling in the blanks with ideas.  At this point it's all very easy and freeform - don't be afraid to write stuff down, as it's only a brainstorming period at this point.  Once you've laid out these major events, you can start filling in the spaces between them...  For that, you'll need technical knowledge.  That's all for now...  try to absorb this stuff, and keep reading the tutorials to come.  Happy hacking!
{% include box-close.html author-name="Radiation" last-modified-on="2006-09-30 21:32:47 +0500" last-modified-by-name="Radiation" %}
