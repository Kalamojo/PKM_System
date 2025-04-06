---
created: 2022-06-08
deadline: 2022-06-30
status: todo
priority: 🟧
hype: 💚
type: project
class: main
children: 2
tags: [timeline, Machine Learning, Python, RL]
banner: "![[Pasted image 20220608112221.png]]"
---


# Machine Learning RPG

## Description
Text-based RPG in python with Machine Learning to power unique storylines and battles. 

## Classes
Players will be able to select a class from a wide range of classes like:
- Rouge
- Mage
- Knight
- Barbarian
- Ranger
With each class comes unique basic stats like health, defense, and attack. Also special stats like stealth, magic, accuracy, and dodge. The most important consequence of the class selection is the starting point of the player's journey. There will be a unique starting area for each and every class, and this will make their adventures very different from the others.

## Storyline
While each class starts off in a completely different area, my hope for the game is for each player to fight the same final boss in the same location. It would be likened to a large map where players can land anywhere, yet all must make their way to the fortress in the center.
However, unlike more standard games, my aim is to create a gaming experience that changes rapidly based on player behavior. I don't wish for a standard loop where a player must *find* the correct course of action to progress in the game.

> [!example] 
> ![[Machine Learning RPG 2022-06-08 11.51.08.excalidraw|300]]

Instead, this process should take *much* longer, and the only **absolute** common thread should be encountering the final boss. I need to devise some way of allowing paths to diverge while still ensuring that they converge eventually. This *could* be done with a lot of hard coding, but this is a Data Science Portfolio project, so I would like to avoid that if possible. Also, I'm lazy.

## Enemies
- Minor opponents will use random chances to decide which moves to use in battle
- Mini-bosses will be hard programmed to make good decisions
- The Final Boss will use reinforcement learning to be the best at its game

Minor opponents will have random names and attributes/stats, but will be based off of the area in which the player finds themself in.

The Final Boss will either:
1. Play against itself countless times to ensure that it knows how to "play" and devises maniacal strategies, or
2. will analyze the player's decisions since the beginning of the game and learn to predict their every move and respond accoringly. When player heals, Boss attacks. When player attacks, Boss shields. When player shields, Boss heals.
The attacking system may be more complex than that, however, and may instead revolve around a system of reloading instead of healing, or maybe adding a completely seperate method for magical spells or ranged attacks.
There may be a way to combine these methods, though I hope to make gameplay as smooth as possible and to avoid training some ginormous model and forcing the player to wait for training. It might be best to pre-train the model with the first option in this case. However, if computation turns out to be a minor issue if one at all, then it would be cool to try this approach:
1. Create a dataset from the player's reactions in battle:
	1. When the player starts, what move do they use first
	2. When the opponent shielded last turn, what do they do
	3. When the opponent attacked last turn, what do they do
	4. When the opponent healed last turn, what do they do
2. Creat a simple classification model that analzes this data and learns how to react in certain situations just like the user.
3. Pit the Boss reinforcement algorithm against this "user-bot" again and again until the Boss knows exactly how user-bot thinks and how to defeat it handily.
This way, beating the Boss will be far from impossible: all the user has to do is break their habbits and try to be unpredictable. I feel like it would be an entertaining challenge, and it would be fun to try and reinvent my approach to battling and try to change myself mid-game.

## Battling
Player will have 3 options during battle:
- Attack
	- Melee
	- Ranged
- Defend
- Heal

Each class has unique attributes for their own battling options. 
- Knights may have fairly high Melee and Ranged attack while having minimal healing.
- Barbarians may have monstorous Melee attack, low Ranged, and standard healing.
- Ranger may have low Melee, monstorous Ranged, and standard healing.
- Rogue may have standard Melee and Ranged, and very high healing.
- Mages will have a spell for their ranged option. These spells will have a high damage, though not as high as Rangers, but will instead come with a special chance for ailment, like maybe life-steal.

Each of these attributes are seperate from base stats like accuracy and defense. Here is a deeper description of the basic options:
- Attack - does damage (and may crit or inflict a status ailment)
- Defend - protects against all direct damage (though after the first use, chances for sucess goes down from 100%, also doesn't block status ailments)
- Heal - restores some health (has a maximum usage for each battle)

## Stats
- Accuracy
- Stealth
- Dodge
- Health
- Armor

### By Class:
```ad-info

| Stat     | Knight  | Mage    | Rogue   | Ranger  | Barbarian |
| -------- | ------- | ------- | ------- | ------- | --------- |
| Health   | High    | Okay    | Bad     | Good    | Monster   |
| Armor    | Monster | Good    | High    | Bad     | Okay      |
| Dodge    | Bad     | High    | Monster | Okay    | Good      |
| Accuracy | Good    | Monster | Okay    | High    | Bad       |
| Stealth  | Okay    | Bad     | Good    | Monster | High      |
```

Every class has the same crit chance.

<span 
	  class='ob-timelines' 
	  data-date='2022-06-08-00' 
	  data-title='ML RPG' 
	  data-class='orange' 
	  data-img = '📎Attachments/📷Images/Pasted image 20220608112221.png' 
	  data-type='range' 
	  data-end='2022-06-30-00'>
	Text-based RPG in python with Machine Learning to power unique storylines and battles
</span>
```timeline-vis
minDate= 2022,05,00
maxDate= 2022,07,00
```
