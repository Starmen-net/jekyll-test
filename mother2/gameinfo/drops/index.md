---
title: Item Drops
categories:
  - mother2
date: 2012-04-06 06:58:55 +0500
---
{% include box-open.html box-id="4401" title="Item Drop Guide - By J_Spade:" author-id="17505" timestamp="2012-04-06 06:58:55 +0500" type="norm" dbname="box51808" last-modified-by="127" %}
<p>Anyone who has played one of the Mother games has no doubt noticed that some enemies drop presents when they are defeated. This is a random occurrence, in that the same type of enemy may not always drop an item when it is defeated. Indeed, some items are so rare that it is perfectly normal for a player to play through the entire game without ever seeing them.</p><br />

Drop Rates:<br />

<p>The odds that an enemy will drop a present when it is defeated are defined as the drop rate for that particular enemy. The drop rate is always some power of 2, over 128. For example, the Spiteful Crow has a rate of 128/128 for dropping a Cookie. (128/128 is a 100% drop rate; you will always get a Cookie when you defeat a Spiteful Crow.) The Struttin’ Evil Mushroom also can drop a Cookie, however its drop rate is only half that of the Spiteful Crow, at 64/128. Note that each type of enemy can only drop a single type of present– neither of these two enemies will ever drop anything that is not a Cookie. (Side note: Sometimes there are multiple enemies with the same name, with very slightly different stats. This can include item drops, and in such cases it is impossible to tell what it is you can expect out of a drop until you actually get the drop.)</p><br />


The RNG:<br />

<p>As with essentially anything computer-based, randomness in Earthbound is handled by the game’s random number generator (RNG). This means that the RNG is responsible for determining whether a defeated enemy drops its present. Additionally, if there are multiple enemies in the battle, it is also responsible for determining which one can drop an item in the first place (more on that in a bit). The RNG is constantly changing behind the scenes, and with essentially every in-game action you take (moving, opening a menu, moving your cursor, etc.), the RNG picks a different random number. When anything requires randomness (such as for item drops), the game asks the RNG what number it’s currently thinking about, and uses that in its calculation. It is worth noting that idling during a battle does not advance the RNG, so if you are emulating the game and use savestates during a battle, you may wish to play with the cursor on the menus in order to introduce more randomness whenever you load the state.</p>

<p>At the very beginning of a battle, before any battling even happens, the RNG throws a random number out, and the game uses that number and the enemy’s item drop rate to determine whether you will get your item. This is important, because it means that the drop is already determined before you defeat the enemy– using Jeff’s Spy command will not change those odds, for example; it will only steal an item that was already set up to drop at the end of the battle.</p><br />


Multiple Enemies:<br />

<p>When you run into an enemy on the field, any nearby enemies will join the battle (if they are able to, based on the game’s preset enemy group combinations). Right at the beginning of the battle, the RNG is used to choose one of the enemies in the group. Each enemy has an equal chance of being selected by the RNG. The enemy that is chosen is the enemy that will have the chance to drop its present. Once the enemy is chosen, the RNG is used again to determine, based on the enemy’s drop rate, whether it will drop the item it can hold.</p>

<p>Note that these calculations have nothing to do with the particular enemy you bumped into on the field. Some believe that only the enemy you bump into can drop an item; this is false.</p><br />


Math and Examples (The Fun Part):<br />

<p>Like anything else involving probability, the odds of enemy item drops can be used in calculating the odds of more specific drop scenarios. (Note: Knowledge of probability and statistics is not necessary to use the information here, but at least a basic understanding is required for a full understanding of the section– not all formulas and definitions used are explained here, however simply they are intended to be made.)</p>

<b>Example #1</b>: Skate Punk and Yes Man Junior:<br />
<ul>
<li>What if you encounter both a Yes Man Junior and a Skate Punk?</li>
<li>The Skate Punk has a 1/128 drop rate for the Pizza, whereas the Yes Man Junior has a 4/128 drop rate for the Bag of Fries.</li>
<li>The RNG can pick either the Punk or the Yes Man with equal probability.</li>
<li>Therefore, we can find the odds of getting either item:</li>
<ul>
<li>odds (Pizza) = 1/128 × 1/2 = 1/256</li>
<li>odds (Fries) = 4/128 × 1/2 = 4/256 = 2/128</li>
<li>odds (either) = 1/256 + 4/256 = 5/256</li>
</ul>
</ul>

<b>Example #2</b>: Two items in a row:
<ul>
<li>What are the odds of getting two Bread Rolls in a row from single Rowdy Mouse?</li>
<li>The Rowdy Mouse has a 4/128 drop rate for the Bread Roll.</li>
<li>Combinations of odds are multiplied, so 4/128 × 4/128 = 16/16384 = 1/1024</li>
</ul>

<p>Sometimes you may wish to know how many enemies you will have to defeat in order to get an item drop. Some might presume, for example, that a drop rate of 1/128 dictates that you will always get the present within 128 attempts. This is unfortunately not how things work. Each drop is independent of the others, and so no matter how many times you’ve missed the drop before, the next drop probability remains unchanged at 1/128. This is called a geometric distribution.</p>

<p>It is usually simpler to calculate probabilities from counts than it is expected counts from probabilities. Therefore, when calculating the number of enemies you expect to have to defeat, it is easier to guess a number and check to see that the probability is something you feel is reasonable.</p><br />

The formula used is fairly easy to use, if you were able to follow so far:<br />

<img src="http://starmen.net/mother2/gameinfo/drops/dropformula.png"></img>, where N is the number of enemies.<br />

<b>Example #3</b>: Sword of Kings:
<ul>
<li>The Sword of Kings is dropped by Starman Supers, with a drop rate of 1/128. As a highly-sought drop, it is probably the most (in)famous of the rare drops.</li>
<li>If we want to know how many Supers we will expect to defeat before finding the thing, we’ll start by making a guess. Let’s try 128– the average case:</li>
<ul>
<li>P = 1 – (1 – 1/128)^128</li>
<li>= 1 – (127/128)^128</li>
<li>≈ 1 – 0.3664</li>
<li>≈ 63.3%</li>
</ul>
<li>Well, that’s better than a coin-flip, but maybe you want a higher degree of certainty:</li>
<ul>
<li>128: ≈ 63.3%</li>
<li>150: ≈ 69.2%</li>
<li>200: ≈ 79.2%</li>
<li>300: ≈ 90.5%</li>
<li>500: ≈ 98.0%</li>
</ul>
</ul>

<p>As you can see, you’re never going to be able to say with 100% certainty that you will obtain any item (with a drop rate less than 128/128), excepting that you are able to say that you will play the game eternally, defeating the same enemy until and beyond the end of time. For the rest of us, choosing a number that gives us a decent degree of certainty is usually going to work out reasonably consistently.</p>

<p>One final bonus challenge for the reader: The Manly Fish’s Brother has a drop rate of 1/128 for the Horn of Life. It always appears alongside the Manly Fish, which has a drop rate of 4/128 for the Beef Jerky. If I want to be roughly 80% sure that I will find at least one Horn of Life by battling the Manly Fish and its Brother, how many battles should I plan to win, and how many Beef Jerkies should I expect to have by then?</p><br />
 
Sources and Further Reading:<br />


Starmen.net Earthbound Walkthrough– Enemy List<br />
<a href="http://walkthrough.starmen.net/earthbound/enemylist_full.php">http://walkthrough.starmen.net/earthbound/enemylist_full.php</a><br />

Starmen.net Earthbound Walkthrough– 1/128 Challenge Guide<br />
<a href="http://walkthrough.starmen.net/earthbound/128.php">http://walkthrough.starmen.net/earthbound/128.php</a><br />

Wikipedia– Geometric Distribution<br />
<a href="http://en.wikipedia.org/wiki/Geometric_distribution">http://en.wikipedia.org/wiki/Geometric_distribution</a>

{% include box-close.html author-name="METC" last-modified-on="2012-04-06 07:27:10 +0500" last-modified-by-name="METC" %}
