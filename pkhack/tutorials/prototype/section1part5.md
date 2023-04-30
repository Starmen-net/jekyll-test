---
title: Prototype&#039;s PK Hack Tutorial
categories:
  - pkhack
date: 2012-02-12 03:11:54 +0000
---
{% include box-open.html box-id="4259" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-12 03:11:54 +0000" type="blank" dbname="box6088" last-modified-by="127" %}
<center><font size="5">1.5 PK Hack's Tools</font></center><br />This is a general run down of the tools, explaining what they let you do. A full explaination of how
to use the tools are in sections 2.0.0, 3.0.0, and 4.0.0. This is just a brief bit so you know what you can do with
JHack.
<br /><br />
<hr />
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 23:20:40 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4260" title="1. IPS Tools and General Tools" author-id="6189" timestamp="2012-02-12 03:12:51 +0000" type="norm" dbname="box15614" last-modified-by="127" %}
The IPS section of JHack contains three tools to help you apply patches, create patches from your hacked ROM to
share with others, and keep track of the patches you have. The first tool will make a patch from the currently loaded
ROM. This is what you share with people on the forums, NOT the ROM itself. DO NOT UPLOAD ROMS! IPS files are smaller,
and have less legal issues. The Patch Applier is for patching ROMs to check out other hacks, or to test your own patch.
Of course you can always use a different patching program.
<br /><br />
The IPS Database keeps track of a number of patches inside of the .jar file JHack uses. If you know enough to
add to that folder inside of the .jar, you can use it to keep track of your own patches and patches you download. Be
warned though, the Six-Character name hack is ROM breaking, do not use it on your hacks!
<br /><br />
The ROM Expander is exactly what it says on the tin. It will increase the size of the EarthBound ROM, giving you
room to work with and add new things or change others. It’s simple, and does the work for you. The Hex Editor is your
friend for getting a look at how things actually look like in the ROM. Also invaluble for doing editing when there is
no tool. The Pointer Editor allows you to edit the pointers for the opening screen’s graphical data, thats it.
<br /><br />
The Reset Button allows you to decompress graphical data for editing outside of JHack, as well as restoring parts
of the ROM to it’s origional state based off of the Backup ROM you specified when you ran JHack. This is a powerful tool
and the only way to access some parts of the game for editing.
<br /><br />
Misc. Crap Editor is just that, it edits a number of variables. From what music plays at some parts of the game,
to starting location, text pointers, Dad’s call timer, and a few other things. It’s fairly easy to use, and should not
be difficult to figure out.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:13:24 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4261" title="2. Items, Item Transformations, Condiments, Stores, Stats, and Teleporting" author-id="6189" timestamp="2012-02-12 03:13:50 +0000" type="norm" dbname="box19501" last-modified-by="127" %}
The Item editor lets you make most changes to items, from stats to who can use, to how many times it can be used,
to if it’s equipable or not, sellable or not, and the name. Items all have an Effect, called an Action. Enemies and
Items all use ASM Actions to do things. More on Actions in 1.5.5. You can also edit the pointer for the “Help Text”,
which is what the item will display when you use the help command on it.
<br /><br />
The Item Transformation Editor is the small bit of code the game uses for the egg hatching into a chick, then
growing into a chicken. You can alter what gets changed into what, what sound effect it uses, and how long the delay is,
but you only have 4 transformations possible.
<br /><br />
The Condiment Editor changes what condiment type items have effect on which food type items. You can change
what goes with what, how much of an effect it has, and how much a bad combination effects HP gain, as well as how much
run time is gained from a skip sandwich.
<br /><br />
The Store Editor is the easy method for changing what items are sold and for how much at the different stores
throughout the game. Keep in mind, if you plan on making NEW stores, you are better off using CCScript, because of how
messed up the stores are. Playing with already used flags can break the stores too, so watch out.
v<br /><br />
The Starting Stats Editor lets you change what level the playable characters start at, as well as what items they
start with, as well as starting money amount. The Level-Up Experience Editor lets you change how much XP is needed for
each level, so you can re-balance the game if you wish.
<br /><br />
The Level-Up Stats Editor is somewhat complex, since the game increases stats based off of a formula.
<br /><br />
Stat gain = ((n * old level) – ((current level of stat – 2) * 10)) * x/50<br />
“n” is the number involved in this tool.<br />
“x” is tricky.<br />
VIT or IQ, level 10 or lower, x = 5.<br />
Everything else, if new level/4, x=7-10, if not, x=3-6.
<br /><br />

HP and PP are gained on level up, using the following formulas:<br /><br />
HP = Random number between 0 and (15*VIT)<br />
PP = Random number between 0 and (5*IQ) Ness gets a rate of (10*IQ) after Magicant.<br />
If the random number is 0, or 1, the system will instead give you a 1, 2, or 3 for HP, and a 0, 1, or 2 for PP.
<br /><br />
Simple right? Changing the numbers in the Stats Editor changes the N in the equation. Don’t feel bad about
not changing this stuff…
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:21:41 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4262" title="3. “Don’t Care” Names, Random Text, Phone List, and Flyover Editing" author-id="6189" timestamp="2012-02-12 03:21:43 +0000" type="norm" dbname="box36794" last-modified-by="127" %}
When using the “Don’t Care” name editor, JHack may ask you if you want to use the 6 character name hack, <b>always
say NO</b>. This is very straightforward, you just change the names someone would get if they hit the Don’t Care selection
during a new game. Just be sure to apply before closing.
<br /><br />
The misc text editor allows you to edit many parts of text that aren’t in the main text block, including all the
naming screen prompts like “Name him.” and “Name him too.”, the names of the different afflictions, battle menu names
(though editing parts of the battle menu require ASM), the names of the different statistics like “Offense:” or “Exp. for
next level.”, and the Lumine Hall text for that sequence. Just keep in mind, if what you are putting into a spot is
longer than what was originally there, you will need to do more work to avoid overwrites.
<br /><br />
The Phone List editor lets you change who you can call when you pick up a phone. There are 6 entries, even
though the game only used 5. The Flag linked to a number must be on for that number to show up in the players phone list,
so you can have some numbers at the start of the game, or use flag manipulation later on to give or take numbers away
from the player. The pointer is the text linked by the number chosen.
<br /><br />
The Flyover editor makes changing the starting flyover sequence easy as can be. The flyover at the beginning of
the game is three parts. The first two are the screen starting at a point on the map and moving in a direction for a
few seconds, followed by the screen blacking out and some text being displayed. The third starts at a point, moves to and
stops at a second point, followed by the screen blacking out and some text being displayed. With this editor you can
change what parts of the map are displayed, the direction of the movement, and the pointer to the text(important if you
are changing the text) and the text itself.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:22:33 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4263" title="4. Text Editor and TPT" author-id="6189" timestamp="2012-02-12 03:22:42 +0000" type="norm" dbname="box17540" last-modified-by="127" %}
The Text editor is the old way of editing Text in EarthBound before CCScript was made. These days, the only real
use for this is to see how the game does things, or to analyse some control codes. It gives you a number of ways of
looking at the text, including how the text is listed by the TPT, the text as it is stored in the blocks, a direct look
at the expanded area(if you’ve expanded your ROM), the text for the Coffee and Tea sequences, and End Credits. Any text
editing done with the editor requires you to understand how text is stored in the ROM, and proper control code usage.
<br /><br />
Just use CCScript, it’s much easier.
<br /><br />
The Text Pointer Table has 1,583 entries. This is how the game keeps track of all the text blocks in the game,
and any text you plan on editing will most likely require you make use of this editor to link the text to various parts
of the game. More detail in how to use this tool is in sections 5.1.4 and 6.8.0.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:23:12 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4264" title="5. Enemy, Action, PSI, PSI Damage, and Battle Entry Editing" author-id="6189" timestamp="2012-02-12 03:23:26 +0000" type="norm" dbname="box39322" last-modified-by="127" %}
The Enemy editor lets you modify almost everything about enemies, from their stats including how much Exp you get
for beating them, what items they drop when beaten, what actions they take in battle, what sprites they use in and out of
battle, what sound is used if you are only fighting them, what weaknesses they have, and a few unknown variables.
<br /><br />
Actions are what enemies and players do during battle. With this editor you can change what they do, how much
they cost, and what text is displayed when the action is used. You can have 318 different actions, but there are only
156 ASM actions that those actions can use. You can not edit ASM actions without learning ASM.
<br /><br />
The PSI editor lets you change the title of the PSI’s, the in-game name, type, an animation setting, what level
characters learn the PSI at, what help text is linked to it, and the ASM action the PSI will take. You can make small
changes, or change some PSI into something completely different like removing Brainshock and instead giving a PSI that
does a Multi-Bottle Rocket attack, has a Bag of Dragonite effect, or acts as a Counter PSI Unit. If you want to change
how much PP a PSI costs, you will need to use the Action editor. The PSI damage alogrithm is hard coded into the ASM,
but you can change a few things about how much damage it does based on the alogrithm using the editor.
<br /><br />
There are 483 battle entries. The editor allows you to edit the associated flag controlling if they should run
away from the player(After the boss of the area is defeated), if this behavior should happen if the flag is set or unset,
the number of enemies initially in the group, and Battle Letterbox size. If you are not sure what that is, look at the
other battle entries and which size they use. You’ll be able to figure it out no problem.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:24:01 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4265" title="6. Sprite, SPT, Playable Sprite Table, and Battle Sprite Editing" author-id="6189" timestamp="2012-02-12 03:24:22 +0000" type="norm" dbname="box34057" last-modified-by="127" %}
Though the list says 4021, you really have fewer sprites to work with. These sprites are all visible as you walk
around the world. The NPC’s, the enemies, the different vehicles, even a few visual effects(Tessie’s water rings, a
flower in Magicant, Star Master’s teleport thingie, ect). The sprites are of different sizes, and it IS possible to edit
the sizes of the sprites outside of the editor, but it can create major problems as well. It is recommended you stick
to the already made sprite’s sizes. You have 8 Palettes TOTAL to work with, 7 of which are actually in use, one is a
duplicate that can be changed without worrying about messing up the sprites already in the game. But if you are editing
many sprites, it is a good idea to plan out the 8 Palettes you will be using beforehand. Remember to limit yourself to
the 8. If you decide to change one color of one palette halfway through, you will need to review all your sprites using
the same palette to make sure you didn’t mess them up.
<br /><br />
The program is as simple as MSPaint. Edit the pixels of the sprite using the 15 colors and the transparent.
1000% zoom is the recommended setting to get a clear idea of how the sprite will look in-game. The tools are easy to use
for anyone who has ever used a graphical editing program. To edit the colors of the palettes, right click on a color and
then click on the RGB tab. Those three numbers are all you need. Feel free to edit the transparent color(the first
color) to any color you wish, just remember it will still be transparent in-game. The last color is the same for every
palette except the fifth palette(moonside usage?). That color is always used for the border around sprites that gives
EarthBound that certain look. If you make sprites without that border, you will notice they look a bit different in-game
than any of the origional sprites. R48,G32,B32 is the “border” color, but it doesn’t always have to be your last color.
It’s just already there in the last spot for almost every palette.
<br /><br />
There are 463 entries in the SPT, or Sprite Pointer Table. The SPT tells the game what sprites are used together
for the characters, linking all of the same sprites together. Some SPT entries have 16 sprites(or mirrored sprites),
others have 8. Many have just 1 sprite linked to 8 times. A few have an idle sprite, making 9 total. SPT entries are
how you place things on the map like NPC’s and whatnot. You can edit the size of the sprites here, but check out
NESluver’s EarthBound Investigations hack, and understand that it leads to ROM instability. Also, Unknown Value #0 is
somewhat understood: <br /><br />

<a href="http://local-static1.forum-files.fobby.net/forum_attachments/0023/2521/spt.txt">http://local-static1.forum-files.fobby.net/forum_attachments/0023/2521/spt.txt</a><br /><br />

This is the list of
values, and how they relate to sprite sizes. The other unknown values….well, good luck. PM me if you know what any
other Unknown Value does.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:26:35 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4266" title="7. Font, Credits Font, Window Border, Window Position, Town Map, and Battle Swirl Editing" author-id="6189" timestamp="2012-02-12 03:27:11 +0000" type="norm" dbname="box41746" last-modified-by="127" %}
Opening the Font editor gives you the option to use a hack that allows for a wider battle font. The editor itself
is very simple and straightforward. You have a number of font’s in the game you can edit, as long as the letter or symbol
is the size allowed. The small line above the drawing area will tell you the border. You have only two options for color,
transparent and black(which will be white in-game).
<br /><br />
The Credits font is for the ending credits, and has 4 colors, but uses two palettes. There are many unused spaces
in this editor, so adding anything new should be problem free. In order to see any changes made with this editor, you need
to trigger the ending credits in-game.
<br /><br />
When starting a game, you are instructed to pick a window flavor. This editor lets you change those flavors.
There are 6 listed in the game, I’m not entirely sure if you can use the extra one listed in the editor. Each Window flavor
has 8 palettes to work with, allowing for a lot of flexablity. You can use this to edit the SMAAAASH!!, YOU WON!, AUTO, HP,
PP, rolling health indicator, and affliction graphics as well. The Window position editor lets you edit the size of the
different windows used by the game, and their location on the screen.
<br /><br />
The Town Map editor lets you change what is shown when the player uses the Town Map in specific areas. You can
change what areas have a map by editing the map sector properties, more info on that is in 1.5.9. The maps are made up of
1 palette, and many small tiles of 64 pixels being arrainged much like the title screen. Most maps tend to have a
checkered background, it is up to you if your maps will have the background.
<br /><br />
If anyone has any experience in using the Battle Swirl editor, PM NESluver or Hyperbound. 
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:27:54 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4267" title="8. Logo Screen, Gas Station Screen, and Title Screen Editing" author-id="6189" timestamp="2012-02-12 03:28:59 +0000" type="norm" dbname="box45830" last-modified-by="127" %}
When editing ANY of the opening graphics, logo, gas station, or title screen, there is a chance of glitching the ROM.
What happens is the ROM will freeze if a button is pressed before the title screen finishes loading. Some people edit the
opening screens with no problems, but it is an issue that exists, so be warned. When importing an image, if it spits up an
error about size, shrink the size of the image, and make sure it has a flat color background, or transparent background.
This will allow the editor to re-use more tiles, giving it a better chance of importing the image without problems.
<br /><br />
The Nintendo, APE, and Halken screens can all be edited using the logo editor, and 4 colors. Though the game uses
grayscale, you can change the colors to any RGB value. The game uses 8 pixel by 8 pixel tiles for these screens, as well as
the gas station and title screens. You can import an image(which is much easier), or create your own in the editor by making
tiles and then placing them on the canvas.
<br /><br />
The Gas Station screen editor is just like the logo screen editor, except you have a LARGE palette to use. 256
different colors can be used on this, allowing this to be easily the most detailed image in your game. You also have the
flash effect, allowing for three palettes of 256 colors, with the first palette being shown, the second palette flashed for a
few frames, and the third palette as the final one. You can also import an image, which is much easier then attempting to
draw tile by tile.
<br /><br />
The Title screen is more complicated than the others. It’s actually two separate parts, and 34 frames of animation.
First is the title screen background. Like the Gas Station screen, you have a 256 color palette to draw from, with a
different palette for each frame. You can use 256 tiles, the screen itself is 32 tiles wide, and 28 high, for 896. Most
likely you will be re-using the background tile MANY times. You can import an image, again easier than going tile by tile.
The title screen text is somewhat different. Here you only have 16 colors to work with, but you still have a different
palette per frame. <b>Keep in mind, if you have the Arrangement Editor Grid Lines enabled, the background will not be at the
correct spot it will be in-game, so be sure to switch it off BEFORE switching to the title screen text.</b> The title screen
text is the foreground of the title screen. Anything you make here will be in front of whatever is on the background. The
people who made EarthBound didn’t do much with it, only doing the flash effect for the letters that they could have done on
just the background. You can put your title screen on the background, then use the foreground for a 34 frame animation.
Granted, the animation is limited to 16 colors, but still nifty.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:30:14 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4268" title="9. Tile, Map, Map Sector Properties, Hotspot, and Door Editing" author-id="6189" timestamp="2012-02-12 03:31:01 +0000" type="norm" dbname="box945" last-modified-by="127" %}
Welcome to the Tileset editor! This is the heart of map editing, and one of the hardest things to do well.
Hyperbound has written a tutorial for his method of putting graphics into a tileset without doing it pixel by pixel as you
have to in this editor, <a href="http://forum.starmen.net/forum/Community/PKHack/46391/page/1">here</a> is the location of it. This will be
discussed later. The main thing to know now is that there are 20 tilesets, and they are used for EVERY location in the game.
All are in use, so if you want to make a new tileset, you must sacrifice an old one. Each tileset has a different number of
16 color palettes. Each tileset is made of minitiles, and tiles with collision properties. Map making is done by placing
these tiles onto the map. This tool is explained in detail in section 2.1.0, including stats, how to make minitiles, what
the collision properties are and how to change them, and how to make a tile out of minitiles.
<br /><br />
The Map editor is JHack’s built-in map editing program. If you have ever used any sort of map making program for
any videogame, you will probably have an easy time picking up on how to use this. The map is HUGE, and made up out of blocks
of tiles, 4 tiles high and 8 wide. All tiles in block MUST be of the same tileset, this is how the game makes boundaries
between the areas. If you have two blocks connected of the same tileset, they will be visible to both blocks in-game. If
you look on the far right hand side of the map you will see most small rooms in the game are a single block, and they are
organized on the map so none of the rooms with the same tileset are touching each other. This is important, if you put your
same tileset rooms all at the same place on the map, you will see every room in-game, and that looks funny. This tool and
map editing is explained in detail in section 2.2.0.
<br /><br />
The Map Sector properties editor lets you modify small details in-game about your maps. Each sector is a tile block
of the map. You can specify if the player can teleport from that sector, if that sector is linked to a town map(and which
map should be pulled up), if the area is considered “indoors”(I think that prevents Escargo Express and Pizza deliveries),
if the player can use Exit Mice, if the player should have Lost Underworld(super small) sprites, the robot sprites, or if
Ness should be using his Magicant sprites, or if Magic Butterfly’s should spawn everytime. There is an unknown variable,
we don’t know what it changes.
<br /><br />
The Hotspot editor lets you edit 54 special locations on the map. These locations can trigger different things in
the game, and are triggered by the player passing into a hotspot. Editing what these hotspots actually DO is another matter
altogether. Anyone with experience in editing what hotspots do please PM Hyperbound or NESLuver with info.
<br /><br />
The Door Editing is a pain, and you are better off trying to edit them in the map editor. When you right click on
a door on the map and choose edit, it will bring up the editor. There are many variables to keep in mind when editing doors.
<br /><br />
First is the type. You can use a switch for puzzles in-game like the one in Scaraba. These are triggered by the
player stepping on them, and unlike actual doors, they don’t move the player anywhere. Instead they link to a text block
that will do whatever you want them to do.
<br /><br />
Rope/Ladder means when your character is on this door, their sprite will change to the one used for climbing ropes
and ladders. You will need a string of these from the bottom to the top of the rope or ladder, all with the ladder type set.
<br /><br />
Actual Door type door spots will move the player to the destination, and can play a sound effect based on which
Style of door you choose. There are many to choose from, test them out in-game to see which you want for which doors.
Some are better for actual doors, some are better for cave openings and the like, and some are good for other methods of
traveling, like falling down a hole.
<br /><br />
Escalator types are interesting. You need two Escalator types for each direction of travel. The first has the
direction the escalator goes, the second is set to Nowhere to prevent the player from going the wrong way. The player
touching the escalator with a direction will move in that direction in line until they reach the Nowhere direction escalator.
<br /><br />
Stair types are a bit like Escalators, except the player can change direction midway. Instead of the Nowhere
direction, the linked stair type uses the opposite direction. So if the stairs run at an angle going SW to NW, the one on
the SW bottom would have a stair type door with the direction of NW, and the one at the top of the stairs would have a
direction of SW.
<br /><br />
Object types link to text. You can consider them sprites that are part of the background, which is what they
effectively are. It allows you to put a text link to part of the background, like a sign. A Person type is effectively
the same.
<br /><br />
Types MUST match! You can’t link Doors to anything besides Doors, Switches to anything besides Switches, and
Objects or People to anything besides Objects. The editor will warn you if you attempt to create a door that has non-
matching types.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:33:09 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4269" title="10. Photo, Music/Flags Correlations, Enemy Placement Groups, and Event-Based Map Changes" author-id="6189" timestamp="2012-02-12 03:33:42 +0000" type="norm" dbname="box48745" last-modified-by="127" %}
There are 32 different photos that can be taken in EarthBound, and with the editor you can edit nearly everything
about all of them. What the center of the picture is, where the Photoman lands, what party members and additional sprites
are allowed to appear in the photo, and what event flag will be tripped when the photo is taken(preventing the photo from
being taken over and over). The photo will be taken when the player steps inside of the yellow box(usually), provided the
flag isn’t triggered. The Photo Movement effects how the photo appears during the slideshow in the ending credits. You
can change the direction and distance the photo will move, this may require much testing to get just right.
<br /><br />
Anyone with any experience dealing with the Music/Flags Correlations editor, please PM NESluver or Hyperbound with
info.
<br /><br />
With 202 entries, the Enemy Placement Groups editor can be a bit overwhelming. Each group has a primary setting
and a secondary setting. The primary setting is what the group is if the associated flag is not set, the secondary is if
the flag IS set. Most groups only use the primary, so when the flag is set, the enemies don’t spawn at all. Others use
the secondary for a later in the game, harder set of enemies. Many of the Onett groups are like this, being mostly crows,
dogs, and snakes, but becoming Starmen later on after the flag gets set. You can also set the encounter rate from rare to
almost always spawns. It is believed that adding enemies to an entry has potential for overwriting, so avoid that if
possible. Try not to use more enemies than were in the group origionally, and try to avoid using a secondary group in
entries that don’t have one by default. Each group has a number of enemies, which are the potential enemy groups that can
spawn in an area you specify in the map editor. These potential enemy groups can be edited in the Battle Entry Editor.
<br /><br />
Event-Based Map Changes gives you an insane amount of control over changing the map over the course of the game.
Changing a single flag can completely change an area of the map, like how the mine appears in the Dusty Dunes Desert. You
simply specify which tile will be changed to which tile, based on if a flag is set or not. If you make this change while
the player is in the area, the change won’t take place until the player leaves and returns. You can have MANY changes linked
to a single flag. Tileset Indoors 4 has 84 changes linked to one flag(the Happy Happyist Cultists in the large room). You
can completely rewrite areas of the map using this tool, hiding areas from the player until a certain point, then revealing
them.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:36:38 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4270" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-12 03:34:44 +0000" type="blank" dbname="box31110" last-modified-by="127" %}
<center><font size="4"><a href="section1part4.php">&larr; 1.4 Technical Details</a> | <b>1.5 PK Hack's Tools</b> | <a href="section1part6.php">1.6 Frequently Asked Questions &rarr;</a></font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 23:47:27 +0000" last-modified-by-name="NESluver" %}
