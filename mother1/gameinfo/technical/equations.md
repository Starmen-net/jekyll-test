---
title: MOTHER / Earthbound Zero Technical Info &amp; Equations
categories:
  - mother1
date: 2011-11-15 05:14:29 +0600
---
{% include box-open.html box-id="4116" title="MOTHER / EARTHBOUND ZERO Equations:" author-id="8286" timestamp="2011-11-15 05:14:29 +0600" type="norm" dbname="box32804" last-modified-by="127" %}
Until recently, the algorithms and equations used in Mother have been shrouded in scary machine code and undocumented assembly code dumps. But luckily, a few awesome people have showed up to save the day and provide us with some very cool and interesting info. The following are how the game makes its decisions and/or makes its various calculations.
{% include box-close.html author-name="Floogal" last-modified-on="2011-11-15 05:15:10 +0600" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="4117" title="Level Experience:" author-id="8286" timestamp="2011-11-15 05:19:04 +0600" type="norm" dbname="box27833" last-modified-by="127" %}
<p>The total experience needed to reach level n = n * n * (n+1) * constant, rounded down.</p>

<p>"constant" depends on person:<br/>
<table border="1" cellpadding="2">
<tr><td>Character</td><td>Constant</td><td>Approximate Decimal</td></tr>
<tr><td>Ninten</td><td>214/256</td><td>0.84</td></tr>
<tr><td>Ana</td><td>203/256</td><td>0.79</td></tr>
<tr><td>Lloyd</td><td>3/4</td><td>0.75</td></tr>
<tr><td>Teddy</td><td>150/256</td><td>0.59</td></tr>
<tr><td>Pippi</td><td>150/256</td><td>0.59</td></tr>
</table></p>

<p>Teddy starts at level 18 with 3600 experience points. Everyone else starts at level 1 with 0 experience points.</p>


{% include box-close.html author-name="Floogal" last-modified-on="2011-11-15 05:53:21 +0600" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="4118" title="Stat Growth Formulas:" author-id="8286" timestamp="2011-11-15 05:34:32 +0600" type="norm" dbname="box30081" last-modified-by="127" %}
<p>Formula for stat increase during a levelup:<br/>
stat gain = (constant + (random number 0-3))/2, rounded down</p>
<p>Constant values:<br/>
<table border="1">
<tr><td>Character</td><td>Fight</td><td>Speed</td><td>Wisdom</td><td>Strength</td><td>Force</td></tr>
<tr><td>Ninten</td><td>4</td><td>4</td><td>4</td><td>4</td><td>4</td></tr>
<tr><td>Ana</td><td>0</td><td>2</td><td>6</td><td>2</td><td>7</td></tr>
<tr><td>Lloyd  </td><td>3</td><td>1</td><td>7</td><td>3</td><td>2</td></tr>
<tr><td>Teddy  </td><td>8</td><td>8</td><td>1</td><td>5</td><td>3</td></tr>
<tr><td>Pippi  </td><td>8</td><td>8</td><td>1</td><td>5</td><td>3</td></tr>
<tr><td>EVE    </td><td>5</td><td>3</td><td>5</td><td>7</td><td>1</td></tr>
<tr><td>FlynMan</td><td>6</td><td>0</td><td>0</td><td>8</td><td>5</td></tr>
</table>
- The latter two start at level 99 with 1,000,000 exp, so those numbers are irrelevant. They also never gain exp from battle, but FlynMan will gain exp from Groucho.</p>
<p>- Increases are regardless of current stat value. Luck can lead to a large variance at higher levels.<br/>
- All stats are capped at 255 and will not overflow.</p>

<br/><hr width="50%"/><br/>
<p>When a levelup is earned, Offense will always increase by an amount equal to the Fight increase.  Similarly, Defense will increase an amount equal to the Speed increase.</p>
<p>Increasing your Fight or Speed in other ways will not increase Offense or Defense.</p>

<br/><hr width="50%"/><br/>
<p>Increases to HP and PP are determined after other stat increases:<br/>
HP/PP gain = random number between 0 and N-1, where N = 2*(target value - current value)<br/>
- regardless of formula, N has a min value of 2, and a max value of 16</p>

<p>HP: Target value = 2*Strength+20 or Strength+255, whichever is smaller.<br/>
PP: Target value = Force*1.5</p>

<br/><hr width="50%"/><br/>
<p>If your level is high enough to learn a particular PSI power, you have a 1/4 chance of learning it after any battle you win or escape from.</p>
{% include box-close.html author-name="Floogal" last-modified-on="2011-11-15 06:04:37 +0600" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="4119" title="Item Information:" author-id="8286" timestamp="2011-11-15 06:05:46 +0600" type="norm" dbname="box54905" last-modified-by="127" %}
<p>The drop rate from enemies is 1/16 for all items.</p>

<p>Infinitely usable items: Super Spray, Flashdark, Bullhorn, AsthmaSpray, WordsO'Love, Swear Words</p>

<p>Breakable items: Fl Thrower, Laser Beam, Plasma Beam, Insecticide, StkyMachine, PSI Stone<br/>
- The probability of an item breaking is always 1/8.</p>

<p>Rope: always hits - the enemy has a 1/4 chance of breaking free each turn.</p>

<p>Bullhorn - always has exactly 50% success-rate.</p>

<p>StkyMachine - inflicts paralysis (like PSI Paralysis)</p>
{% include box-close.html author-name="Floogal" last-modified-on="2011-11-15 06:19:25 +0600" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="4120" title="Battle Formulas:" author-id="8286" timestamp="2011-11-15 06:13:00 +0600" type="norm" dbname="box62787" last-modified-by="127" %}
<p>Physical attacks (using "FIGHT" option):</p>

<p>Dodge rate: [26 + (target's Fight - attacker's Fight)/2]/256<br/>
Smash rate: [26 + (attacker's Fight - target's Fight)/2]/256</p>

<p>Damage done is approximately equal to Attacker's Offense - (Defender's Defense / 2).<br/>
However, if attacker's offense &#60; defender's defense, then damage is ((Attacker's Offense * 3) - Defender's Defense) / 4<br/>
- Damage with SMAAAASH hits ignores the target's defense.</p>

<br/><hr width="50%"/><br/>

<p>Status Ailment Accuracy:</p>

<p>Probability of evading status ailments: [(defender's Strength or Force)/2]/Attacker's Wisdom</p>

<p>- Strength is used to avoid Darkness, Poison and Paralysis.<br/>
- Force is used to avoid Puzzled, Confused and Hypnosis.<br/>
- StoneOrigin ALWAYS causes Stone if it hits a non-immune target (it can miss, though).<br/>
- Ninten will ALWAYS have an asthma attack when hit by a car exhaust.  While affected, the only action he can take is to use an Asthma Spray.<br/>
- The same formula is used for status ailments inflicted via PSI, items, or enemy special attacks.</p>

<br/><hr width="50%"/><br/>

<p>The higher a character's Speed is, the better chance it has of going first.</p>

<p>The chance of running is 50/50. Each character may make an attempt to run once per turn, and on a success, the whole party flees.  PSI 4th-D Slip works 100% of the time.</p>
{% include box-close.html author-name="Floogal" last-modified-on="2011-11-15 06:31:37 +0600" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="4122" title="Random Encounters:" author-id="8286" timestamp="2011-11-15 06:34:04 +0600" type="norm" dbname="box1449" last-modified-by="127" %}
<p>Whenever you take a step in an area with random encounters, the RNG generates a number, and you get into a battle if the number is below a certain amount. Here is the list of random encounter probabilities:<br/>
1: 32/256<br/>
2: 21/256<br/>
3: 16/256<br/>
4: 13/256<br/>
5: 10/256<br/>
6: 8/256<br/>
7: 6/256<br/>
8: 5/256</p>

<p>To decide which one to use, the game takes the number associated with the tile you stepped on (between 1 and 8), adds a "bonus", and uses the probability attached to that number.</p>

<p>The bonus resets to 0 everytime you enter a no-encounter area, and increases by 1 each time you get into a fight.  The bonus can't go higher than 2, and it can't increase the category number higher than 8.</p>

<p>Example: You leave a safe town to enter a field full of tiles marked with "2".<br/>
- With every step you take, you've got a 21/256 (or about 8.2%) chance of getting into a fight.<br/>
- Once you get into your first fight, the odds of getting into your second fight for that area are 16/256 (6.25%) for each step.<br/>
- After that second fight, your odds for getting into a fight remain at 13/256 (about 5.1%) for each step for the remainder of your exploration of the area.  The "bonus" resets when you go back to the safe town.</p>
{% include box-close.html author-name="Floogal" last-modified-on="2011-11-15 06:35:19 +0600" last-modified-by-name="Floogal" %}
