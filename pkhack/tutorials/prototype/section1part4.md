---
title: Prototype&#039;s PK Hack Tutorial
categories:
  - pkhack
date: 2012-02-12 03:04:27 +0000
---
{% include box-open.html box-id="4253" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-12 03:04:27 +0000" type="blank" dbname="box39576" last-modified-by="127" %}
<center><font size="5">1.4 Technical Details</font></center><br /><br /><font size="2">This is all important info for editing the EarthBound ROM, understanding how things work, how the ROM
stores things, and how the SNES handles the data. You won’t be able to do more than the most simple of hacks
if you don’t know this material. If you are experienced at ROM hacking or programming, much of this may be familiar,
but I would still recommend reading the sections on Control Codes and Terms. If you have no experience with either,
read and understand this section.</font><br /><br /><hr />
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 23:49:29 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4254" title="1. The ROM and SNES Info" author-id="6189" timestamp="2012-02-12 03:05:30 +0000" type="norm" dbname="box43820" last-modified-by="127" %}
The unaltered EarthBound ROM is 3 MB’s, or 24 Mb, and has a header of 8001008000000000aabb04, followed by 502
(in decimal) hex bytes of 00. The CRC32 is DC9BB451. This can be expanded to 4MB’s, or 6MB’s. The ROM has a piracy
screen that can be tripped, most hackers need not worry about that. Editing the opening screens will cause the ROM
to freeze if the player presses any buttons before the Title Screen is finished loading. By default the game starts
with Ness in his PJ’s and with no enemies, flags need to be changed for a different beginning state. The ROM uses
internal control codes to change flags, manipulate items, change the map(limited, explained later), deal with windows,
load data into memory, and do many other functions. The SNES has four background layers, but EarthBound only uses
one. The SNES supports up to 32,768 colors, but Sprites can only have 16 colors(one is usually transparent as well),
this is a limitation of the SNES, not the ROM. The SNES sound setup supports 8 channels at once, meaning 8 different
instruments can be used in a song. The ROM is jam packed, so when adding ANYTHING new or making something larger
in size data-wise, it MUST be put in the expanded area(past the end of the origional ROM).
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:05:56 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4255" title="2. Control Codes and Palettes" author-id="6189" timestamp="2012-02-12 03:06:10 +0000" type="norm" dbname="box19555" last-modified-by="127" %}
Almost everything that isn’t graphics or audio is done with Control Codes. You don’t need to memorize them,
but it is important that you have the reference list handy for working with them. When the game reads a text block,
the codes tell the game how to act. Data Crystal has the current list, but there are still some codes we don’t know,
and others we don’t fully understand. Use the current list to understand how the game does things you want to do.
If there is a part of EarthBound’s event’s you don’t understand, you search the text for whatever is closest to the
event you want to decipher. Then you use the list to translate the block of text into how the game did things. This
is slow at first, but before too long you will know the common codes and won’t need to look them up.<br /><br />
The SNES, and the ROM by extension, use what’s known as the 15-bit RGB color space. This covers 32,768 colors
but the SNES can only use 15 colors and a transparent for each sprite, and background. This 16 total color group is
known as a Palette. You have many Palettes to use, some of which appear unused, but you may not have more than 15
colors and a transparent per Palette. You will be face to face with the Palette when editing sprites, tilesets,
or any other graphical work. When changing colors, the easiest way to do it is to click on the RGB tab, and use those
values. 0-255 is valid for each of the three.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:06:50 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4256" title="3. Hex and Addresses" author-id="6189" timestamp="2012-02-12 03:06:33 +0000" type="norm" dbname="box65367" last-modified-by="127" %}
Hexadecimal is a base 16 mathmatic system. You are used to using Decimal, a base 10 system. Understanding
Hex is key to understanding how pointers work, and anything related to pointers like linking text. Decimal has the
numbers 0, 1, 2, 3, 4, 5, 6, 7, 8, 9. The next number is one place over, with the smallest number back to 0, 10.
Hex has the numbers 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F. Then comes 10. What comes before 20? 1F. A is
10, B is 11, C is 12, D is 13, E is 14, and F is 15. 10 is 16. Base is how many digits a numbering system has including
zero. So a base 10 system has 10 digits, and a base 16 system has 16. A calculator(most OS’s have one) that can convert
Hex to Dec and back will be very helpful to you. Google Lunar Address, it does the job for you.
<br /><br />
Hex is important because that’s how the SNES stores data. The ROM is 3MB’s, and counting forward from
0×000200/$C00000, the game and ASM reference other parts of the game based on it’s address. An address with a 0x before
it is a Hex address. You could open any Hex editor, open the EarthBound ROM in it, and go to the Hex address. But the
game doesn’t always use addresses in the form of Hex. Most of the time it uses the SNES ROM address, which has $ before
it, as well as being offset. To make matters even more fun, the pointers tend to be stored backwards making it easy
to get confused. The way to translate the ROM addresses and pointers is in section 1.4.7.
<br /><br />
Hex is shown in pairs of 2 digits. These two hex digits are a single hex byte. Everything from 00 to FF is a
valid hex byte, and occupies one space of the ROM’s data. You may remember how I was talking about the header of the ROM?
80 01 00 80 00 00 00 00 aa bb 04 is how it looks in the Hex Editor. The header is not counted by the SNES as being
part of the usable ROM for the game. Everything below Hex Address 0×000200 counts as SNES Address $000000. This
table might help explain it:
<br /><br />
0×000000/$000000 = 80<br />
0×000001/$000000 = 01<br />
0×000002/$000000 = 00<br />
0×000003/$000000 = 80<br />
0×000004/$000000 = 00<br />
0×000005/$000000 = 00<br />
0×000006/$000000 = 00<br />
0×000007/$000000 = 00<br />
0×000008/$000000 = AA<br />
0×000009/$000000 = BB<br />
0×00000A/$000000 = 04<br />
0×00000B/$000000 = 00<br />
all 00 bytes up to<br />
0×0001FF/$000000 = 00<br />
0×000200/$C00000 = 9C<br />
0×000201/$C00001 = 0C<br />
0×000202/$C00002 = 28<br />
0×000203/$C00003 = A2<br />
0×000204/$C00004 = 0C<br />
and so on.<br />
<br />
And naturally, Control Codes are at least 1 Hex byte if not more. Pointers are 3 Hex bytes, since an address is
6 Hex digits. The entire game can be altered through Hex, provided you know how to do it. You can also cause the most
destruction to your ROM with the Hex Editor. The ROM’s address range is 0×000000-0×3001FF or $000000-$EFFFFF, with
0×000200-0×3001FF or $C00000-$EFFFFF being the usable area in an unedited, unexpanded, legit ROM. When you expand it to
4MB, the end range gets moved up to 0×4001FF or $FFFFFF. When you expand it to 6MB, things get different. The 3MB and
4MB versions of the ROM both are HiROM SNES ROMs. They use the area of SNES addressing $C00000-$FFFFFF, except the 3MB
doesn’t go up that high. The 6MB ROM uses the ExHiROM system, using SNES addressing areas $C00000-$FFFFFF and
$400000-$7DFFFF, with the ROM using $400000-$5FFFFF as 0×400200-0×6001FF. Because that’s not confusing at all.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:08:10 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4257" title="4. Pointers, Tables, Binary Flags, and Events" author-id="6189" timestamp="2012-02-12 03:08:52 +0000" type="norm" dbname="box38540" last-modified-by="127" %}
A Pointer in the simplest sense is a hex address. It tells the SNES/ROM to go to location B. B being whatever
the address is. The EarthBound ROM uses many control codes as pointers, but one of the most common is 08. Hence,
whenever you see [08 XX XX XX], you know to check out whatever is at that address. Pointers are a hackers friend, since
a pointer is always the same size. Given that the game uses many pointers to keep track of parts of the ROM, you can
change a pointer, and tell the game to look somewhere else. A normal pointer will tell the game to go to the new
location, then come back and continue from where it left off once it hits a 02 in the new area. A Jump Pointer does
not, instead the game will go to the new location, run until it hits a 02, then stop. Any other text in the old area
will not be parsed by the game if it uses the Jump Pointer.
<br /><br />
For example, 2F137B-2F13CA=Map Data: Tile Collision Pointer Table, 2F13CB-2F141A=Map Data: Tile Animation
Pointer Table, and 2F141B-2F146A=Map Data: Freakish Tile Animation Pointer Table are all tables of Pointers. They are
a list of nothing but addresses. The third list points to a table of control codes for map animations. By changing
these pointers to a new list located in the expanded area, we can make the list longer in size without worrying about
overwriting something else. The great thing about pointers is you can change them without worrying about overwriting
since they are always 6 digits, or 3 hex bytes.
<br /><br />
Tables are generally stored in the ROM with no frills. XX XX XX, XX XX XX, XX XX XX, etc. This makes them easy
to spot, and change. The ROM uses tables for many parts of the game, including map animation, graphical data, tileset
locations, and they all can be changed and the data being pointed to can be altered in any way, as long as the new data
sits in the expanded area. Most of the tables the ROM uses have been identified, and can be found on the ROM map on
Data Crystal.
<br /><br />
Flags are how the game sets conditions and keeps track of what’s been done and what is still waiting to happen.
A flag is a single Hex byte, and usually used as a Boolean argument. 00 is an off flag, 01 is an on flag. Many parts
of the game use flags and change flags while the game is being played. Talking to someone, moving to a different area,
even battles can flip flags on or off and change the game. A flag is always 00 or 01, all other single hex byte
arguments are called variables, since they can be different values. For example, the variable the game uses as short-
hand for a party character is either 00, 01, 02, or 03 depending on who it is. The game starts with all the flags in
a certain state, with some being on, and some being off. Flags control sprite visiblity and the presense of enemies,
so from the start of a new game you won’t see any enemies. The game changes the flag through a text block or event or
door or something shortly after. The flag list at Data Crystal will tell you what flags do what, or at least the ones
that are known. Rufus also made a patch for EarthBound called EB++, which adds many more usable flags, so you don’t
need to be limited, or worry about using a flag that has triggered effects on the game like the previously mentioned
sprite visiblity. Just keep in mind that version 0.2 of the patch and up conflict with Mr. A’s map editor, and can’t
be used together.
<br /><br />
Flags are indexed in the ROM with two Hex bytes, XX XX being the flag, the flag data being either 00 or 01. Flags
are listed in the Data Crystal list by their index. The game always references flags by it’s index. You really should
understand flags well before trying to hack.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:09:31 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4281" title="5. IF, ELSE, IF/ELSE, and other concepts" author-id="6189" timestamp="2012-02-20 23:42:25 +0000" type="norm" dbname="box6706" last-modified-by="127" %}
The IF statement is a programming concept going back to the start of programming. Is X larger than Y, yes or no.
The question gets asked, and the IF statement returns a result of 0 or 1, no or yes. The program then does something
due to the result it got. It’s like saying “Stop, is X true? If so, do this.” If false, it just continues forward.
The ELSE statement is similar to the IF, but with a small change. Question gets asked, result gets returned, but what
the program does is different. Instead of doing something if the result is true, it does nothing. It only activates if
the result is false. It’s like saying “Stop, is X true? If not, do this, otherwise keep going.” An IF/ELSE tree can be
created in this manner, much like that godawful Stores IF/ELSE tree.
<br /><br />
For example, lets say my characters are getting near the end of the game, and I want each character to get a
bonus to stats if they have a specific item in their inventory. They step on a hotspot which triggers a text block I
have set up, which then uses the Control Codes and Pointers to run through a tree, checking each character for their item
and awarding the bonus if they have it, or skipping past them if they don’t. Control Code [06 XX XX YY YY YY YY]
checks a flag and then redirects the game to Address YY YY YY YY. [09 XX (YY YY YY YY)] is a very useful code, since
it lets you set a group of addresses, with the address being used selected by XX being compared to the value in whats
known as Working Memory. This code uses XX to determine how many addresses it will use. Thus,[09 03 will look like
[09 03 YY YY YY YY YY YY YY YY YY YY YY YY]. You can manipulate what’s in memory with other control codes and text
editing, info on that later. By doing so you can control which address the game picks. [08 XX XX XX XX] and
[0A XX XX XX XX] are both direct pointers to something, but 08 will have the game come back to the original location
and continue once it encounters the 02 End of Line code in the pointed to area, whereas 0A will just stop once it hits
the 02.
<br /><br />
It is important to understand how a program flows to understand how EarthBound works. Much of the graphical
and sound work is done through ASM, as well as some operations like actions an enemy takes during battle. Most other
aspects of how the game functions is done through text blocks, flags, events, hotspots, and the SPT and TPT. Most work
in text blocks is done with Control Codes. Check the Control Code list on Data Crystal for an idea of what can be
accomplished with Control Codes. The game uses a Control Code to open a window, print text, wait for user input, do
something in relation to the input received, and close the window. There may be many more control codes in that simple
text block changing flags, giving items, removing items and much more. CCScript will handle the majority of your
Control Code work for you, but if you ever need to look at how the game does something, or need to do something with a
Control Code you know but can’t figure out in CCScript, then you need to know some things about how the ROM stores it’s
text data.
<br /><br />
Thanks to Messianic for this info.
Every block of text can be considered a “line”. A line is 100 units, with 256 spaces available to it. For
example, take a line in the expanded area, say f40000 for example, that is one line, the next one up is f40100, then
f40200, etc. In between each of these is 256 spaces, because that’s what a line contains. So, if I enter 56 units
worth text “size” into f40100, then it will now create a new line underneath itself for exactly 200 spaces, mainly 00‘s
and a 02 to end it. This new line will start at that 57th space, so it will be started at f40139, since 54 in decimal is
39 in hex. If I enter some text here, and it doesn’t take up the full 200 left over space sizes, it will now create
another new line under itself for the remainder of available spaces. So technically you could have 256 one sized spaces
within every “line” of 100.
<br /><br />
Basically you can go into any of the raw text and write whatever you want, as long as in the end all the places you
edited still come out to the same number of lines and add to 256. If I edit a line that starts of the 80th sized space
of a set of 256, that is currently 40 sizes long, and I make it 26 spaces long, in order not to crash the rom, I need
to make the very next line an extra 40 sizes bigger in order to get the math back to 256 for the set, this will eat up
the newly creates space.
<br /><br />
For example. Ever get those extra blankish lines being created in places of text when you don’t want them there? Mad
simple. Click on them and look at their size. Do the math to add to 256.
<br /><br />
Example:
I go to line f45500 in my expanded text. I write something 95 sizes big. This means under it a line of 00 and 02 will be
created for exactly 161 sizes. Later on in the hack I don’t like it my text there. I delete 35 spaces out of it. OH NO!
Now there is ANOTHER line created BETWEEN the two of them, for those 35 spaces I at up. What do I do now? You have 2
options. You can keep a blank space separating you text by going to the middle line and typing enough 00 followed by
the ending 00 to make up the difference between you new text line of 60 spaces and the total needed be reached of 256
by making it 196 sizes long. OR, if you want to see nothing but text in your editor without spaces in between, then
type enough 00’s in sequence IN THE SAME LINE as your text AFTER IT ENDS until you hit exactly 256.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-20 23:43:13 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4282" title="6. Memory Registers and RAM Manipulation" author-id="6189" timestamp="2012-02-20 23:46:40 +0000" type="norm" dbname="box31800" last-modified-by="127" %}
Thanks to whoever put this info on Data Crystal.
If you think things were complicated before, now we get into the nitty gritty just short of ASM. Every window
has a number of what is called Memory Registers. Every window has the following six “registers”, divided into two parts:
<br /><br />

Active Memory
Working Memory (4 bytes)
Argumentary Memory (4 bytes)
Secondary Memory (2 bytes)
<br /><br />
Storage Memory
Working Memory Storage (4 bytes)
Argumentary Memory Storage (4 bytes)
Secondary Memory Storage (2 bytes)
<br /><br />
Storage Memory is simply used to store copies of the registers in Active Memory. The only thing that can be
done with it is to copy values to and from Active Memory using codes 1B 00 and 1B 01. Working Memory is generally
used to hold return values from control codes, and is also used in controlling program flow. Argumentary Memory
(also called Argumentative Memory) is usually used to pass values to control codes. That’s why it’s called
“argumentary”, because it contains the argument of the control code in programming terms. Secondary Memory isn’t
used very much, but it is used in forming simple loops and can be used as an extra register, since it can be copied
to and from the other active registers.
<br /><br />
Most of the work you can do with the Memory Registers is with Control Codes, and they are places where you can
store data, manipulate what’s there, and supply the return variable or flag from other Control Codes for controlling
program flow. An argument is what gets returned, and/or specified in the code. Control Code [06 XX XX YY YY YY YY]
uses XX XX for an argument, whereas [0B XX] and [0C XX] use XX as an argument, but return 00 or 01 into Working Memory,
turning that into an argument for the next code to check Working Memory. Most Control Codes take some form of an
argument, there is a listing of common arguments on Data Crystal.
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-20 23:47:39 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4283" title="7. Terms, Labels, and Conversion Rates" author-id="6189" timestamp="2012-02-20 23:48:01 +0000" type="norm" dbname="box13120" last-modified-by="127" %}
Argument = A variable used for comparison to something else in programming.<br />
Assembly = 65816 Assembly code. This is the variant of ASM that the SNES uses, with which you can do anything
you can code that the SNES and ROM are capable of.<br />
Action = Actions that are taken during battle. This term means the entire action including name and stats, not
just the ASM.<br />
Background = Behind the Sprites is this.<br />
Break = End of Line for text, usually closes the window as well.<br />
Boolean = Binary, 0 or 1, yes or no.<br />
CC = Control Code.<br />
Color Value = RGB code for a color, ie 0,0,0 or 255,255,255.<br />
Collision = How the game knows where you can walk, and what’s a wall.<br />
Events = When you beat a certain enemy, walk to a certain spot, or go through a certain door, usually a flag
will be changed to reflect that so the game keeps track of what’s been done already so it doesn’t send a boss at you
the next time you go through the area.<br />
Flags = Indexed in XX XX format, single Hex byte Boolean variables.<br />
Hexadecimal = Base 16 numeric system, common in computer programming.<br />
Header = The first 200(hex) bytes of a ROM, can’t be used for storage due to the way the SNES handles ROM data.<br />
Index = A part of the ROM that is organized a certain way, but doesn’t have a table.(Is there a flag table?)<br />
Mini-Tile = 8 Pixel by 8 Pixel square, used in the Map and other Background images, there are 512 minitiles in a
tileset.<br />
Memory Register = Some small variables you can access and manipulate, this counts as RAM not ROM.<br />
Parsing = When going through a text block, the game runs through it from the beginning to the end in sequence,
unless a control code says otherwise. This is known as parsing.<br />
Palette = 15 colors and a transparent. Different parts of the game have different palettes you can use. For
example, the sprites in the game all use the same 8 palettes, but tilesets have differing numbers of palettes they can
use.<br />
Pixel = 1×1 block of color, smallest graphical unit.<br />
Pointer = An address to elsewhere on the ROM that makes the game start parsing at the new address.<br />
Range = The start to the finish of something.<br />
RAM = EarthBound and the SNES both have RAM which can be accessed and manipulated, but will not be saved once
someone turns the game off.<br />
ROM = The EarthBound ROM, which you are editing.<br />
SPT = Sprite Pointer Table.<br />
TPT = Text Pointer Table.<br />
Table = Usually a list of pointers, but sometimes contains more or different data.<br />
Tile = A tile is 16 minitiles in 4×4 order.<br />
Tileset = A tileset is both the minitiles, and the tiles they form. There are 20 tilesets you can use.
<br /><br />
When working with a 3 or 4 MB ROM, knowing that the first 200 Hex bytes are header, the first byte of the ROM is
0×000200/$C00000. So to convert a Hex Address to a SNES Address, subtract 200 Hex, then add C00000 Hex. Lets give that
a try. Say you were going to mess around with the PSI Names List at 0×158F7A, but needed to know the SNES address of it.
158F7A – 200 = 158D7A + C00000 = D58D7A. Pretty simple huh?
<br /><br />
When working with a 6 MB ROM, things get a little bit trickier, and I highly recommend you use Lunar Address to
do your conversions. Working with anything from 0×000200 is still the same, but everything from 0×400200 and up uses a
different mapping. So while 0×158F7A is $D58D7A, 0×458F7A is $458D7A, since the second address mapping starts at $400000.
The second mapping is an easier conversion since you only need to subtract for the header, but still a pain.
<br /><br />
Now lets look at how the ROM stores pointers, so you know how to convert what is there to an address you can use.
5d e5 df 00 is a pointer. 5d e5 df is also a pointer. The pointer is actually only 3 hex digits, but the game sometimes
will tack on another digit(always 00) to space them apart in tables. But $5DE5DF is not where that pointer goes, I don’t
even know if that is a valid SNES address. The game stores the pointers backwards by digits, so 5D E5 DF is actually
$DFE55D, or 0×1FE75D. So when changing a pointer, first the pointer must be in SNES Address format, then break it into 3
digits of 2, and reverse their order. AB CD EF becomes EFCDAB, 12 34 56 becomes 563412, and 0×235EFA becomes E35CFA,
which becomes FA 5C E3. If you plan on doing any work with pointers like editing text or enemies, you should know how
to convert the addresses around.<br /><br />

If the idea of reversing pointers confuses you, here is a nifty little animated graphic made by Jeffman to help you along:<br /><br />

<center><img src="http - //starmen.net/pkhack/tutorials/prototype/images/bytereverse.gif" /></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-03-11 23:51:55 +0000" last-modified-by-name="NESluver" %}

{% include box-open.html box-id="4258" title="New Box, Edit me :(" author-id="6189" timestamp="2012-02-12 03:09:58 +0000" type="blank" dbname="box64732" last-modified-by="127" %}
<center><font size="4"><a href="section1part3.php">&larr; 1.3 Editing Order</a> | <b>1.4 Technical Details</b> | <a href="section1part5.php">1.5 PK Hack's Tools &rarr;</a></font></center>
{% include box-close.html author-name="NESluver" last-modified-on="2012-02-12 03:36:58 +0000" last-modified-by-name="NESluver" %}
