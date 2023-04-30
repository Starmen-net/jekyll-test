---
title: MOTHER 2 / EarthBound Anti-Piracy Measures
categories:
  - mother2
date: 2007-06-23 01:58:11 +0000
---
{% include box-open.html box-id="3083" title="MOTHER 2 / EarthBound Anti-Piracy Measures" author-id="288" timestamp="2007-06-23 01:58:11 +0000" type="norm" dbname="box54491" last-modified-by="127" %}
<b>Update: For a more thorough description in layman's terms, see this article on EarthBound Central: <a href="http://earthboundcentral.com/2011/05/earthbounds-copy-protection/">EarthBound's Copy Protection</a></b>

<br /><br />
Most game companies these days put checks in their games to thwart -- or at least curb -- software pirates from illegally distributing and selling their work. This includes the MOTHER 2 and EarthBound games. Here is a brief look at the measures the programmers took to prevent piracy of these games and how we came to figure them out.

<br /><br /><hr width="70%" /><br />
<b><u>Multiple ROM Versions:</u></b><br />
It's common for game companies to release slightly different versions of games without telling anyone. These different versions often fix rare bugs and glitches, and because of this, different versions of game ROMs aren't uncommon.
<br /><br />
There appeared to be at least two different versions of the EarthBound ROM, but nobody really knew <i>how</i> they were different, until early 2007. It was discovered that one version actually had its anti-piracy measures crippled, meaning that version was looked at by pirates and hacked to keep the game from realizing it was pirated. The other version appeared to be a clean dump of an EarthBound cart. There may be other versions of clean EarthBound ROMs, but so far we don't have any details on that possibility.

<br /><br /><hr width="70%" /><br />
<b><u>The Actual Anti-Piracy Measures:</u></b><br />
Forum user Goplat looked at the differences between the two ROMs, and found that the files differed by only a few bytes here and there. These spots were where the anti-piracy code was. So, by looking at the clean ROM, he could see what those snippets of code did:
<ul>
 <li>A subroutine at address $C0A11C is the first line of defense against pirates, being called upon startup. It first checks to make sure that there's only 8 kilobytes of SRAM, the part of memory used to hold saved games. Cartridge copiers have more, so if it detects that, the game displays a screen that says, "It is a serious crime to copy video games."</li>

 <br /><br />
 <li>Both games also check which kind of PPU the SNES has - if it's a PAL type (used mainly by European game systems), they display the following screen:<br /><br /><center><img src="palcheck.png" /></center></li>

 <br /><br />
 <li>Movement Script 1 calls a subroutine at $C1FFD3, which takes a checksum of the code at $C0A11C-$C0A150. If anything in that memory range has been altered, a non-zero value is stored to $7EB539, and the script will then bring up a copyright infringement screen. This screen differs between MOTHER 2 and EarthBound.<br /><br /><center><img src="m2copyright.png" /> <img src="ebcopyright.png" /></center></li>

 <br /><br />
 <li>At $C0281A there's a check to see if $7EB539 is zero. If it isn't, random enemies appear MUCH more often. This was probably an attempt to make the game unenjoyable. Here are screenshots of just how many enemies will show up:<br /><br />
<center><img src="enemies01.png" width="256" height="223" /> <img src="enemies02.png" width="256" height="223" /> <img src="enemies03.png" width="256" height="223" /> <img src="enemies04.png" width="256" height="223" /> <img src="enemies05.png" width="256" height="223" /> <img src="enemies06.png" width="256" height="223" /> <img src="enemies07.png" width="256" height="223" /> <img src="enemies08.png" width="256" height="223" /> <img src="enemies09.png" width="256" height="223" /> <img src="enemies10.png" width="256" height="223" /> <img src="enemies11.png" width="256" height="223" /> <img src="enemies12.png" width="256" height="223" /> <img src="enemies13.png" width="256" height="223" /> <img src="enemies14.png" width="256" height="223" /> <img src="enemies15.png" width="256" height="223" /></center></li>

 <br /><br />
 <li>At $C08391 is another SRAM checker. We're not sure when it's called, or what the game does if it detects more than 8 kilobytes. It's called from six different places though, so it probably happens at various events throughout the game, much like how the piracy checks on EarthBound Zero worked.</li>

 <br /><br />
 <li>At $C3FDC5 is another checksum routine that goes through $C0A11C-$C0A150. This one is called after Pokey turns off the Devil's Machine. If any data in that range has been changed, the checksum fails, the game deletes all your saved games (seriously) and then it crashes/freezes up. Neat. You can see it in action here:<br /><br /><center><youtube src="BmyoV1bkXNI" /></center></li>
</ul>

<hr width="70%" /><br />
<b><u>This is so cool! I wanna try it out!</u></b><br />
If you want to try this stuff out yourself, use the following code in the cheat section of your favorite emulator:<br /><br />

<center><font size="6"><b>C3FDDAD0</b></font></center>

<br />
Or if you have a Game Genie, the code is:<br /><br />

<center><font size="6"><b>2DE2-546E</b></font></center>

<br />
<b><font color="red">CAUTION!</font></b> If you decide to try out these codes, make a backup of your .srm file! That's the file that has your save games!
{% include box-close.html author-name="Tomato" last-modified-on="2011-05-14 19:25:34 +0000" last-modified-by-name="Tomato" %}
