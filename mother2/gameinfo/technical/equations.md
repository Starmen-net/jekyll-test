---
title: MOTHER 2 / EarthBound Technical Info &amp; Equations
categories:
  - mother2
date: 2007-01-21 12:31:49 +0600
---
{% include box-open.html box-id="2798" title="MOTHER 2 / EarthBound Game Equations:" author-id="288" timestamp="2007-01-21 12:31:49 +0600" type="norm" dbname="box3376" last-modified-by="127" %}
Until recently, the algorithms and equations used in EarthBound have been shrouded in scary machine code and undocumented assembly code dumps. But luckily, a few awesome people have showed up to save the day and provide us with some very cool and interesting info. The following are how the game makes its decisions and/or makes its various calculations.
{% include box-close.html author-name="Tomato" last-modified-on="2007-06-22 15:02:56 +0500" last-modified-by-name="Ninten1" %}

{% include box-open.html box-id="3074" title="General Battle Equations & Algorithms:" author-id="849" timestamp="2007-06-20 16:21:09 +0500" type="norm" dbname="box46430" last-modified-by="127" %}
<u><b>Instant Wins</b></u>
<br /><br />
In some cases, when you get into a fight with a weak enemy, you automatically win without going into battle. This is based on your speed, offense, and status. Only the chosen four matter for this; NPCs such as Flying Man are not counted.
<br /><br />
You can't instantly win in a red swirl or in a fight triggered by dialogue (such as a boss fight). If the number of enemies is greater than the number of characters who aren't unconscious, diamondized, paralyzed, nauseous, poisoned, possession, mushroomization and don't have a sunstroke or a cold you can't instantly win.
<br /><br />
In a black swirl, the highest speed among enemies is compared to the lowest speed among your current party members (even if unconscious). Each enemy's HP+defense is then compared to the lowest offense among your current party members (even if unconscious). If your party's stats are greater (not equal) in both cases, you instantly win the fight.
<br /><br />
In a green swirl, your characters who do not suffer from the aforementioned statuses are sorted by offense in descending order, and the enemies are sorted by HP in descending order. In turn, each character "attacks" the first enemy which is still "alive", dealing exactly 2*offense-defense "damage". If every enemy is "killed" this way, you instantly win the fight.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Item Drops</b></u><br/><br/>
When you enter a battle (or after YOU WIN! appears on an instant win), an enemy is chosen at random, and then that enemy may or may not decide to drop an item, with probability depending on the enemy.  Since the item drop is decided before the battle begins, enemies summoned/called to help cannot drop anything.<br/><br/>
If you spy on any enemy, you will always pick up the predetermined item (if there is one), regardless of who is actually spied on.

  If Jeff's inventory is full, however, not only will Jeff neglect to collect the item, but the game will not indicate that there is an item to pick up.<br/><br/>
If a Cute Li'l UFO or Beautiful UFO is present in battle and no item would be dropped otherwise, an item is randomly chosen from a list of 7. This item will always drop.  If both enemies are present, the Beautiful UFO drops an item. This obviously doesn't matter, since those two enemies will never appear in the same region.
<br/>
- Cute Li'l UFO: Cookie, Bag of fries, Hamburger, Boiled egg, Fresh Egg, Picnic lunch, Pizza
<br/>
- Beautiful UFO: Can of fruit juice, Royal iced tea, Protein drink, Kraken soup, Bottle of water, Cold remedy, Vial of serum
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Turn Order</b></u>
<br /><br />
At the beginning of each turn, each character has their speed adjusted by +/- 50% to determine the turn order. In the case of a tie, later characters act first, and enemies act before allies. If an enemy tries to steal, they will always act last.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Auto Fight</b></u>
<br /><br />
Paula and Jeff will always attack a random enemy. If Ness/Poo is not feeling strange or unable to concentrate, he will attempt to use PSI if applicable. The possible PSI commands for Ness and Poo in Auto Fight are used in the following priority order. As soon as an action is reached which is possible and fits the conditions, it is used and the rest are not considered. If both Ness and Poo use PSI, they will not target the same character. Lifeup Omega isn't considered to target anyone for this purpose. When more than one character can be targeted, the character with the lowest absolute HP has priority. A character is considered to be at low HP if his/her HP is less than 1/4 of maximum.
<br /><br />
1. Lifeup Omega if more than one PC is alive and all have low HP
<br />
2. Lifeup gamma on someone with low HP
<br />
3. Lifeup beta on someone with low HP
<br />
4. Lifeup alpha on someone with low HP
<br />
5. Healing Omega on an unconscious character
<br />
6. Healing gamma on a paralyzed character
<br />
7. Healing gamma on a diamondized character
<br />
8. Healing gamma on an unconscious character
<br />
9. Healing beta on a poisoned character
<br />
10. Healing beta on a nauseated character
<br />
11. Healing beta on a crying character
<br />
12. Healing beta on a character who is feeling strange
<br />
13. Healing alpha on a character with a cold
<br />
14. Healing alpha on a character with sunstroke
<br />
15. Healing alpha on a sleeping character
<br /><br />
If none of these options are available, Ness/Poo will attack a random enemy.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Run Away</b></u>
<br /><br />
The probability of successfully running away from a fight is (highest speed among PCs - highest speed among enemies + 10*turn number)%. Some enemies prevent you from running away regardless of your speed.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Avoiding mortal damage:</b></u>
<br /><br />
If an ally has more than 1 HP and is dealt damage that would kill you, the probability of surviving with 1 HP instead is guts/500 or 1/20, whichever is greater.  Enemies can't use guts to survive otherwise mortal damage, but NPCs can.
<br /><br />
If only one PC is alive when the last enemy dies, and that enemy has a damaging final action (such as bursting into flames), that damage will set the character's HP to 1, even if it wouldn't otherwise kill him. This is mostly irrelevant, since the battle will end before this will matter.
<br /><br />
Everyone's HP stops decreasing at the beginning of the last enemy's death text (or when the game declares that you've successfully run from a battle), and increases back to 1 if it's at 0 (for those that are still alive).  If anyone is recovering health at one of these times, their HP will keep increasing to the proper value, at an accelerated rate.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Calling for help</b></u>
<br /><br />
The odds of help arriving is (maximum number of enemy type - number of enemy type)/(maximum number of enemy type) * 205/256. (205/256 is probably an approximation of 4/5.) If the enemy being called doesn't exist in the current formation, help will not arrive. This is why there are formations with 0 of an enemy (such as 1 Skate Punk, 0 Pogo Punk, 0 Yes Man Junior).
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Enemies running from you</b></u>
<br /><br />
Enemies will run away from you out of battle under the following circumstances:
<br /><br />
- Some event flag is set (because a sanctuary boss was killed): always
<br />
- Sum of your levels > enemy's level*10: always
<br />
- Sum of your levels > enemy's level*8: 75%
<br />
- Sum of your levels > enemy's level*6: 50%
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>General note about randomness</b></u>
<br /><br />
Whenever numbers are adjusted by +/- 25% or +/- 50%, the result follows a pyramid-shaped distribution. The number is more likely to be near the middle of the range than near either end, when considering intervals of equal length.
<br /><br />
{% include box-close.html author-name="Ninten1" last-modified-on="2017-01-17 05:45:35 +0600" last-modified-by-name="CerealQueen" %}

{% include box-open.html box-id="2799" title="Bash/Shoot and Defend Equations & Algorithms:" author-id="288" timestamp="2007-01-21 12:33:46 +0600" type="norm" dbname="box12433" last-modified-by="127" %}
<u><b>Physical Attacks</b></u>: Attacks are dealt with as follows:
<br /><br />
<b>1. Miss</b>
<br /><br />
Each weapon and NPC/enemy has a miss rate. Unarmed PCs have a miss rate of 1/16. Crying and/or nausea will increase this miss rate by 8/16. If the weapon misses, skip the remaining steps.
<br /><br />
<b>2. SMAAAASH!</b>
<br /><br />
With the Bash command or Bash-like enemy/NPC attacks, the probability of a SMAAAASH! is equal to guts/500 or 1/20, whichever is greater. If a SMAAAASH is successful, it deals 4*offense-defense damage, and skip the remaining steps. (Yes, even step 5.) This damage is still affected by defending if applicable. If the target had a physical shield, it will be depleted.
<br /><br />
<b>3. Dodging</b>
<br /><br />
The target has a (2*target speed - attacker speed)/500 chance of dodging the attack. If the enemy dodges, skip the remaining steps.
<br /><br />
<b>4. Damage</b>
<br /><br />
The attack will deal (attack level * offense - defense) +/- 25% damage. Bash, Shoot, and enemy/NPC projectile attacks have attack level 2, while Bash-like attacks can attack levels 1, 2, 3, and 4, depending on the attack.
<br /><br />
<b>5. Status</b>
<br /><br />
If the attack was Bash or a Bash-like enemy/NPC attack, the target will stop feeling strange if it was feeling strange.
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Defend</u></b>
<br /><br />
Defending or having a physical shield halves damage from some attacks -- defending while also having a physical shield will reduce damage from relevent attacks by 3/4.
<br/><br/>
Following is a list of the only attacks that are affected by defending or physical shields -- defending & physical shields are useless for all other attacks.  Note that many other attacks still have their damage reflected by power physical shields, but the "shields" are only useful for offensive purposes in those cases.
<br/>
- standard bash attack (NOT shooting attacks)
<br/>
- come out swinging
<br/>
- scratch with one's claws
<br/>
- throw a punch
<br/>
- freeze you in time
<br/>
- start a continuous attack
<br/>
- attack with a crushing chop
<br/>
- brandish a knife
<br/>
- claw with one's sharp nails
<br/>
- swing one's tail very hard
<br/>
- wield a shopping bag
<br/>
- swing a club
<br/>
- swing one's hula hoop
<br/>
- use one's misery attack (unused attack)
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>What the messages mean when a regular attack misses</u></b><br/><br/>
When it says "Ness dodged swiftly!", it's due to speed.
<br/>
When it says "...narrowly missed hitting the target!", it's due to miss rate from Shoot or a similar attack.
<br/>
When it says "Just missed!", it's due to miss rate from Bash or a similar attack.
{% include box-close.html author-name="Tomato" last-modified-on="2010-07-15 04:34:00 +0500" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="3075" title="PSI Equations & Algorithms:" author-id="849" timestamp="2007-06-20 16:26:16 +0500" type="norm" dbname="box60868" last-modified-by="127" %}
<u><b>PSI Rockin' Miss Rate:</b></u> Ness's PSI Rockin' (or whatever you named your favorite thing) misses sometimes. The probability it'll miss is calculated by:
<br /><br />
<center><b>(((2 * target's speed) - Ness's speed) / 5)%</b></center>
<br />
This will give you PSI Rockin's miss percentage. Say that Ness's speed is 50, and you're fighting a Spiteful Crow, which has a speed of 77 (taken from the <a href="http://starmen.net/mother2/ebdb/enemies.php?enemy=158">EBDB</a>). Plug in those numbers and calculate it out, and you'll see that PSI Rockin' will miss 20.8% of the time, on average, in that situation.
<br />
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Flash</b></u>
<br /><br />
For each enemy it hits, it causes one of several effects, depending on which Flash you used.
<br /><br />
<b>Flash alpha</b>
<br />
7/8: uncontrollable crying
<br />
1/8: feeling strange
<br /><br />
<b>Flash beta</b>
<br />
5/8: uncontrollable crying
<br />
1/8: feeling strange
<br />
1/8: paralysis
<br />
1/8: instant death
<br /><br />
<b>Flash gamma</b>
<br />
4/8: uncontrollable crying
<br />
1/8: feeling strange
<br />
1/8: paralysis
<br />
2/8: instant death
<br />
<br /><br />
<b>Flash Omega</b>
<br />
3/8: uncontrollable crying
<br />
1/8: feeling strange
<br />
1/8: paralysis
<br />
3/8: instant death
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Freeze</b></u>
<br /><br />
Has a 25% chance of solidifying the target
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Thunder</b></u>
<br /><br />
Thunder randomly chooses a target, then tries to affect it. The probability of Thunder working is:
<br /><br /><center><b>(number of enemies)/4</b></center>
<br /><br />
If Thunder kills an enemy and still has some shots left, this probability will not decrease. If Thunder hits an enemy with a PSI shield, the shield will be depleted.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Magnet</b></u>
<br /><br />
Magnet drains an amount of PP in the range 2-8 with a pyramid-shaped distribution. It can't drain more PP than the target has. Magnet Omega will ignore NPCs, while alpha merely fails due to lack of PP.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Offense Up</b></u>
<br /><br />
Offense up will fail if the target is a NPC. Otherwise, it will increase the target's offense by 1/16 of its current value, rounded down and capped below at 1, up to a maximum of 5/4 of the target's unmodified offense.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Defense Down</b></u>
<br /><br />
Defense down will fail with probability luck/80, or always if it targets a NPC. If it hits, it will reduce the target's defense by 1/16 of its current value, rounded down and capped below at 1, down to a minimum of 3/4 of the target's unmodified defense.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Healing gamma</b></u>
<br /><br />
Healing gamma has a 3/4 chance of reviving an unconscious character.
{% include box-close.html author-name="Ninten1" last-modified-on="2007-06-20 16:47:06 +0500" last-modified-by-name="Ninten1" %}

{% include box-open.html box-id="3079" title="Pray Formulas & Algorithms:" author-id="849" timestamp="2007-06-20 17:10:22 +0500" type="norm" dbname="box40262" last-modified-by="127" %}
Praying has one of several random effects:
<br /><br />
5/16: subtle light, heals each PC by 1/16 of maximum HP, rounded down
<br />
2/16: warm light, heals each PC by 1/8 of maximum HP, rounded down
<br />
1/16: mysterious light, restores (5 +/- 50%) PP to each PC
<br />
1/16: golden light, heals a random living PC by the difference between their maximum HP and Paula's current HP
<br />
1/16: dazzling light, same effect as Rockin beta to a random enemy
<br />
2/16: dazzling light, same effect as Flash alpha to all allies and enemies
<br />
1/16: rainbow-colored light, revives all dead allies and enemies to full HP
<br />
1/16: mysterious aroma, put all allies and enemies to sleep
<br />
1/16: heaven rending sound, make all allies and enemies feel strange
<br />
1/16: heavy air, same effect as Defense down alpha to all allies and enemies
<br /><br />
The mysterious aroma and heaven rending sound ignore resistance to Hypnosis and Brainshock respectively.
<br/><br/>
The rainbow-colored light will revive not only all defeated enemies that were present at the start of the battle, but also any enemies that were called to battle and later defeated.
{% include box-close.html author-name="Ninten1" last-modified-on="2010-07-15 04:45:27 +0500" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="3862" title="Mirror:" author-id="8286" timestamp="2010-07-15 05:34:05 +0500" type="norm" dbname="box58269" last-modified-by="127" %}
Mirror copies every byte of the enemy's data except:
<br/>
- HP (current/rolling/maximum)
<br/>
- PP (current/rolling/maximum)
<br/>
- whether the character is ally or enemy
<br/>
- row / character number (the same byte is used for both, one for enemies and one for allies)
<br/>
- enemy number (possibly represents the type of enemy; not 100% sure)
<br/>
- whether the character has acted already this turn.

<br/><br/>

Poo also copies enemy stat modifications and status ailments (or lack thereof).  Any changes to Poo's status (e.g. becoming poisoned or losing his sunstroke) will be maintained after battle.
<br/><br/>

The exp/gold values are copied, so if Poo is diamondized while mirroring an enemy, that would theoretically add to the exp/gold gained at the end of battle. The death routine handles PCs differently, but diamondization does not.
<br/><br/>

If Poo transforms into an enemy with a fixed AI (like Ghost of Starman), his "turn counter" will be equal to the enemy's, no matter what turn Poo transforms. So Poo and Ghost of Starman would always do the same attacks on the same turns.
<br/><br/>

If Poo transforms into an enemy with a death action (like Nuclear Reactor Robots exploding), he won't do it himself if he dies.
  If Poo dies while transformed, he will still be in that form if you revive him in the same battle.
<br/><br/>

Mirror wears off naturally after 16 turns, if the Neutralizer (or equivalent attack) is used, or at the end of battle.
<br/><br/>

The failure-rate for Mirror depends on the enemy.  It never works on bosses and some other enemies, and never has a success-rate higher than 50%.  Mirror will always fail if the target isn't an enemy or if the target is a NPC.
{% include box-close.html author-name="Floogal" last-modified-on="2010-07-15 05:36:39 +0500" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="3076" title="Item Equations and Algorithms:" author-id="849" timestamp="2007-06-20 16:28:01 +0500" type="norm" dbname="box48037" last-modified-by="127" %}
<u><b>Bottle Rockets:</b></u><br/><br/>A standard bottle rocket will miss with probability (2*target's speed - Jeff's speed)%. If it hits, it will deal (120 +/- 25%) damage.
<br/>Big bottle rockets and Multi bottle rockets will try to hit 5 and 20 times respectively, with the same miss rate. When they hit, they deal ((120*number of hits) +/- 25%) damage.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Bombs/Bazookas</b></u>
<br /><br />
Bombs and Super Bombs will deal (90 +/- 50%) and (270 +/- 50%) damage respectively to the target. They also deal splash damage to the characters or enemies on either side of the main target: (45 +/- 50%) and (135 +/- 50%) respectively.  The (Heavy) Bazooka is simply a reusable (Super) Bomb.
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>(Hungry) HP-sucker:</u></b> has a luck/80 chance of failing against the target, and always fails if Jeff is confused and targets himself, or his HP is rolling down to 0. If it hits, it will suck HP equal to (target's maxHP/8) +/- 50%. This does not count as damage, so it will ignore Master Belch's immunity to damage, and won't wake sleeping enemies. Jeff's new HP is set by adding the amount drained to his current rolling HP.  A confused Jeff can accidentally steal HP from his allies.
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Insecticide/Xterminator Spray:</u></b> has a luck/80 chance of failing against the target, and always fails if the target isn't an enemy or isn't an insect. They deal 100 +/- 50% and 200 +/- 50% damage respectively.
<br /><br />
<b><u>Rust promoter (DX):</u></b> has a luck/80 chance of failing against the target, and always fails if the target isn't an enemy or isn't metallic. They deal 200 +/- 50% and 400 +/- 50% damage respectively.
<br /><br />
<b><u>Counter-PSI Unit:</u></b> fails with probability luck/40, and always fails against NPCs or when the target already can't concentrate.
<br /><br />
<b><u>Shield killer:</u></b> fails with probability luck/80, and always fails (irrelevantly) if the target doesn't a shield or PSI shield.
<br /><br />
<u><b>Dragonite:</b></u>This deals 800 +/- 25% damage to each enemy, and is fire elemental.<br/><br/>
<u><b>Defense Shower and Defense Spray</b></u> work exactly the same as Offense Up, except on defense instead of offense.  They always fail against NPCs.
<br/><br/>
<u><b>Slime Generator, Monkey Love, Toothbrush, Stag Beetle, Dirty Socks</b></u> will fail to solidify the target with probability luck/80, and always fail against NPCs.
<br/><br/>
<u><b>Handbag Strap and Mummy Wrap</b></u> miss with probability (2*target speed - attacker speed)/250. It deals precisely 100-defense (handbag strap) or 400-defense (mummy wrap) damage, and will solidify with 100% accuracy if it hits & does damage.  They always fail against NPCs.<br/><br/>
<u><b>Pharaoh's Curse and Viper</b></u> always poison the target (NPCs are immune).<br/><br/>
<u><b>Snake and Snake Bag</b></u> miss with probability (2*target speed - attacker speed)/250. If it hits, it deals a random amount of damage from 1 to 4, and has a 1/2 probability of causing poison (NPCs are immune).
<br/><br/>
<u><b>Yogurt Dispenser</b></u> misses with probability (2*Target Speed - Attacker Speed) / 250. If it hits, it deals a random amount of damage from 1 to 4.
<br /><br /><hr width="50%"/><br /><br />
<u><b>Lucky Sandwiches</b></u><br/><br/>
When you buy a Lucky Sandwich (more precisely, immediately before the text "Lucky sandwich? Who is going to carry this?"), the game chooses from one of six Lucky Sandwich item entries to use.  The recovery effect of a Lucky Sandwich is set in stone once bought, so it's possible to stockpile certain types.<br/><br/>
Generate a random number 0-15. If less than 7, 60 HP sandwich.<br/>
Else generate a random number 0-8. If less than 4, 240 HP sandwich.<br/>
Else generate a random number 0-4. If less than 3, full HP sandwich.<br/>
Else generate a random number 0-1. If 0, 5 PP sandwich.<br/>
Else generate a random number 0-2. If nonzero, 20 PP sandwich.<br/>
Else full HP+PP sandwich.<br/><br/>
Probabilities:<br/>
60 HP: 44% (21/48)<br/>
240 HP: 25% (12/48)<br/>
full HP: 19% (9/48)<br/>
5 PP: 6% (3/48)<br/>
20 PP: 4% (2/48)<br/>
full HP+PP: 2% (1/48)
{% include box-close.html author-name="Ninten1" last-modified-on="2010-07-15 05:31:34 +0500" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="3863" title="Resistences:" author-id="8286" timestamp="2010-07-15 05:40:16 +0500" type="norm" dbname="box6005" last-modified-by="127" %}
Every playable character, NPC, and enemy has a unique resistence to fire, freeze, flash, paralysis, and hypnosis, ranging from 0 to 3.  For fire & freeze, the corresponding resistences to damage from such attacks are: 0 -> 0%, 1 -> 30%, 2 -> 60%, 3 -> 95%.  For flash & paralysis & hypnosis, the corresponding evasion to the attacks are: 0 -> 1%, 1 -> 50%, 2 -> 90%, 3 -> 100%.
<br/><br/>
There is no brainshock resistence stat stored for anyone.  Instead, it is calculated at the start of battle to be (3 - (hypnosis resistence)).  Thus, it is impossible for anything to be immune to both hypnosis & brainshock -- one of the two will always work with at least a 50% success-rate.
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Arm equipment</u></b> is the only way to alter hypnosis/brainshock resistence for the chosen 4.  Without wearing any arm equipment, they will have 1% hypnosis protection & 100% brainshock protection.  Only 4 pieces of arm equipment will alter this, and nothing will provide 100% hypnosis protection.
<br/><br/>
<b><center><table border="1">
<tr><td>Equipment</td><td>Hypnosis protection</td><td>Brainshock protection</td></tr>
<tr><td>Pixie's Bracelet</td><td>1</td><td>2</td></tr>
<tr><td>Cherub's Band</td><td>2</td><td>1</td></tr>
<tr><td>Goddess Band</td><td>2</td><td>1</td></tr>
<tr><td>Bracer of Kings</td><td>2</td><td>1</td></tr>
<tr><td>everything else/unarmed</td><td>0</td><td>3</td></tr>
</table></center></b>
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Body and Other equipment</u></b> alter Fire, Freeze, Flash, and Paralysis resistence.  Without wearing any such equipment, the chosen 4 will have resistences of 0% for fire & freeze & 1% for flash & paralysis.  The resistances of the Body and Other equipment (in the range 0-3) are added together. If the sum is more than 3, it is 3 instead. The usual formula is then used. Combining the Diadem of Kings with a Star Pendant would give full protection for paralysis, flash, freeze, and fire (all of which the Star Pendant alone will give anyway). Combining it with an Earth Pendant instead will also give full protection for flash, freeze, and fire (1+2=3), as well as the 50% paralysis protection from the Diadem of Kings.
<br/><br/>
<b><center><table border="1">
<tr><td>Equipment</td><td>Fire</td><td>Freeze</td><td>Flash</td><td>Paralysis</td></tr>
<tr><td>Travel Charm</td><td>0</td><td>0</td><td>0</td><td>1</td></tr>
<tr><td>Great Charm</td><td>0</td><td>0</td><td>0</td><td>2</td></tr>
<tr><td>Crystal Charm</td><td>0</td><td>0</td><td>0</td><td>3</td></tr>
<tr><td>Rabbit's Foot</td><td>0</td><td>0</td><td>0</td><td>3</td></tr>
<tr><td>Night Pendant</td><td>0</td><td>0</td><td>3</td><td>0</td></tr>
<tr><td>Rain Pendant</td><td>0</td><td>3</td><td>0</td><td>0</td></tr>
<tr><td>Flame Pendant</td><td>3</td><td>0</td><td>0</td><td>0</td></tr>
<tr><td>Earth Pendant</td><td>2</td><td>2</td><td>2</td><td>0</td></tr>
<tr><td>Sea Pendant</td><td>3</td><td>3</td><td>3</td><td>0</td></tr>
<tr><td>Star Pendant</td><td>3</td><td>3</td><td>3</td><td>3</td></tr>
<tr><td>Diadem of Kings</td><td>1</td><td>1</td><td>1</td><td>1</td></tr>
<tr><td>Cloak of Kings</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
<tr><td>everything else/unarmed</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>
</table></center></b>
{% include box-close.html author-name="Floogal" last-modified-on="2010-07-15 06:00:14 +0500" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="3077" title="Status Equations & Algorithms:" author-id="849" timestamp="2007-06-20 16:50:52 +0500" type="norm" dbname="box54938" last-modified-by="127" %}
<b><u>Overwriting statuses</u></b>
<br /><br />
Some combinations of statuses can't coexist. When an effect tries to add a status to someone who already has a status of the same type, the one with the lower number wins. The statuses are:
<br /><br />
<b>Permanent statuses:</b>
<br />
1. Unconsciousness
<br />
2. Diamondization
<br />
3. Paralysis
<br />
4. Nausea
<br />
5. Poison
<br />
6. Sunstroke
<br />
7. Cold
<br /><br />
<b>Special statuses:</b>
<br />
1. Mashroomization
<br />
2. Possession
<br /><br />
<b>In-battle statuses:</b>
<br />
1. Sleep
<br />
2. Uncontrollable crying
<br />
3. Immobilization
<br />
4. Solidification
<br /><br />
<b>Coexisting statuses:</b> (all of these can coexist with each other and the other 3 categories of statuses)<br/>
- Feeling strange<br/>
- Unable to concentrate<br/>
- Homesickness
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Diamondization</b></u>
<br /><br />
Uses the same resistance probability as Paralysis.  The one exception is the "biting hard" attack, which diamondizes the target with probability (80 - target's luck stat)/80 if the attack hits and doesn't SMAAASH!<br/><br/>
You get experience and money from diamondized enemies.  If you try to target a diamondized enemy, your attack will instead hit a random non-diamondized enemy; multi-target attacks will simply ignore diamondized enemies.
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Nausea and Poison</u></b>
<br /><br />
Nausea and poison deal 20 +/- 25% damage each turn in battle and deal 10 damage every 2 seconds out of battle.<br/><br/>
Nausea has the additional effect of increasing the character's miss rate by 8/16 (like crying).
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Cold and Sunstroke</u></b>
<br /><br />
Colds and sunstroke deal 4 +/- 25% damage each turn in battle and deal 2 damage every 4 seconds out of battle.<br /><br />
Approximately every 20 seconds, if you're in a desert area and you don't have any permanent status ailments other than a cold, you have a (30-guts)% chance of getting a sunstroke, with a minimum of 1%.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Homesickness</b></u>
<br/><br/>
Any full status cure will cure homesickness. This includes being healed by a sanctuary, hot springs, the Mr. Saturn hospital, as well as Dungeon Man and a few one-time events.  Of course, you can also heal homesickness by talking to Ness's mom directly or via a telephone.
<br /><br />
Whenever you win a battle (but not an instant win), Ness has a certain probability of becoming homesick. The probability depends on Ness's level.
<br /><br />
Level 1-15: 0/256
<br />
Level 16-30: 3/256
<br />
Level 31-75: 2/256
<br />
Level 76-99: 0/256
<br /><br />
If Ness is homesick, he has a 1/8 chance of losing his turn in battle.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Possession</b></u><br/><br/>
Possession always fails against NPCs and enemies.  Paula's rainbow-colored light prayer effect will revive a defeated Tiny Li'l Ghost, but since it doesn't reinflict possession on your party members, the ghost will be gone after the battle.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Sleep</b></u>
<br /><br />
A sleeping character can't do anything. If you are asleep and are dealt damage from an attack, you have a 1/2 chance of waking up.  Otherwise, there is a 1/4 chance of waking up naturally on his/her/its turn.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Immobilization</b></u>
<br /><br />
An immobilized character can't use weapons or items, much like being paralyzed. An immobilized character has an 85% chance of becoming able to move on his/her/its turn.
<br /><br /><br /><hr width="50%"/><br /><br />
<u><b>Solidification</b></u>
<br /><br />
A solidified character can't do anything. A solidified character will always become able to move on his/her/its turn.
{% include box-close.html author-name="Ninten1" last-modified-on="2010-07-15 04:47:36 +0500" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="3861" title="NPCs:" author-id="8286" timestamp="2010-07-15 04:36:30 +0500" type="norm" dbname="box19398" last-modified-by="127" %}
NPCs ("Non-playable Characters") are everyone that appear on your team at one point, but are not one of the Chosen 4, and are not controllable.  This includes Teddy Bears, Super Plush Bears, and Tiny Li'l Ghosts.
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Damage to NPCs</u></b><br/><br/>
NPCs are completely immune to all status ailments and stat modifications (both good & bad).  They can be protected by shields, and reflect damage back with them.
<br/><br/>
Attacks that do anything besides inflict ordinary damage will completely fail against NPCs.  This includes attacks that have both a main damage-dealing effect & a secondary effect (bite using poisonous fangs, bite hard, PSI Freeze) -- NPCs will not only ignore the status ailment, but they also won't take ordinary damage, either.
<br/><br/>
NPCs can have HP stolen from them with the HP Sucker.
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Targetting NPCs</u></b><br/><br/>
Most NPCs are non-targettable, meaning that enemies won't choose to attack them, and your party can't target them with defensive moves (PSI Shield alpha, Defense Spray, etc.).  However, anyone who's mushroomized or feeling strange may randomly target an NPC with any move.
<br/><br/>
By contrast, targettable NPCs (Flying Man, Teddy Bear, Super Plush Bear) are targetted by enemies 75% of the time, while a random party member is chosen the remaining 25% of the time.
<br/><br/>
Multi-target attacks will hit all playable characters & NPCs normally, regardless if the NPCs are targettable or not.
{% include box-close.html author-name="Floogal" last-modified-on="2010-07-15 04:42:18 +0500" last-modified-by-name="Floogal" %}

{% include box-open.html box-id="3078" title="Stat Equations & Algorithms:" author-id="849" timestamp="2007-06-20 16:59:59 +0500" type="norm" dbname="box57749" last-modified-by="127" %}
<u><b>Level Up</b></u>
<br /><br />
When you gain a level, the increase of stats other than HP and PP is given by the formula:
<br /><br />
<b><center>Stat gain = ((growth rate * old level) - ((stat-2) * 10)) * r/50</center></b>
<br /><br />
r is given by one of the following:
<br />
* If the stat is vitality or IQ, and the new level is 10 or lower, r=5.
<br />
* Otherwise, if the new level is divisible by 4, r is a random number from 7 to 10.
<br />
* Otherwise, r is a random number from 3 to 6.
<br /><br />
HP and PP are based on vitality and IQ respectively. HP tries to increase to 15*vitality, and PP tries to increase to 5*IQ normally or 10*IQ for Ness after Magicant. If either of these results in a gain of less than 2, the stat instead gains by a random number in the range 1-3 (HP) or 0-2 (PP).
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Special Messages when levelling up</u></b>
<br /><br />
HP up at least 20: "Sweet!"
<br/>
PP up at least 8: "That rocks!"
<br/>
other stat up at least 3: "Oh, baby!"
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Stat growth rates by character</u></b><br/><br/>
The "growth rate" variable used in the level-up formula depends on the the character and specific stat.<br/><br/>
<b><center><table border="1">
<tr><td> </td><td>Ness</td><td>Paula</td><td>Jeff</td><td>Poo</td></tr>
<tr><td>Offense</td><td>18</td><td>12</td><td>10</td><td>21</td></tr>
<tr><td>Defense</td><td>5</td><td>3</td><td>6</td><td>18</td></tr>
<tr><td>Speed</td><td>4</td><td>8</td><td>5</td><td>7</td></tr>
<tr><td>Guts</td><td>7</td><td>5</td><td>5</td><td>3</td></tr>
<tr><td>Vitality</td><td>5</td><td>2</td><td>3</td><td>4</td></tr>
<tr><td>IQ</td><td>5</td><td>7</td><td>9</td><td>4</td></tr>
<tr><td>Luck</td><td>6</td><td>5</td><td>4</td><td>3</td></tr>
</table></center></b>
<br /><br /><br /><hr width="50%"/><br /><br />
<b><u>Extra info</u></b><br/><br/>
Offense and defense are capped at 255, but other stats will just overflow to 0 if you exceed 255. All stats except vitality and IQ are protected from underflows, surprisingly enough.  Mid-battle, offense & defense can be temporarily increased above 255 via PSI Offense Up and other such methods.
<br/><br/>
After completing Magicant, Ness gets a boost to his stats as follows:<br/>
+20 Speed<br/>
+15 Guts<br/>
+10 Vitality<br/>
+15 IQ<br/>
+20 Luck<br/><br/>
Stat boosts from items (capsules and Rock Candy), Magicant, and equipment are ignored in the level-up formula (exluding HP/PP).
{% include box-close.html author-name="Ninten1" last-modified-on="2010-07-15 05:44:46 +0500" last-modified-by-name="Floogal" %}
