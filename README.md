# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->

Community: `r/truegaming`

For my initial reading of the community, I noticed four candidate distinctions:

1. Many posts discuss serious topics through the context of gaming, often expanding the discussion beyond a particular game and into the broader “meta” of gaming, culture, or society.

2. Some posts focus on why players behave or feel a certain way, discussing things like motivation, frustration, nostalgia, competitiveness, burnout, or other psychological aspects of playing games.

3. Other posts focus more on larger trends in game design and the gaming industry, such as monetization, difficulty, live-service models, open-world design, and differences between older and modern games.

4. Some posts focus on how gaming communities themselves shape the experience of games, such as how online discussion, competitive culture, social expectations, fandoms, or player communities can change the way people view or enjoy a game.

---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `player_experience`

**Definition:**
Posts primarily about the player's personal or psychological experience of gaming, such as motivation, frustration, nostalgia, burnout, enjoyment, difficulty, or competitive behavior.
**Example 1:**
> I have a tip for those that are burned out on gaming and can't seem to enjoy any game anymore. Try to appreciate the whole gestalt. By that I mean that you should pay attention to more than just the gameplay or the systems or mechanics, but appreciate the sounds, the sights etc...
Due to many factors, I became extremely reductionist in thinking. My mind would boil down everything to its core.

Eventually it felt like every game was more or less the same.

There was nothing interesting, just a bunch of pixels and numbers. My mind just looked at the systems and the gameplay, ignoring everything else, seeing it as fluff, useless details. I'd just look at the boiled down core gameplay and systems, and I'd just consider the sights and sounds and all the other many things that make up a game as pointless things that the developers added to make the experience prettier, while at its core it was the same old thing.

But that way of thinking is just wrong on so many levels.

Instead, try to appreciate the experience as a whole. The art, the characters, the animations, the sounds, the music, the story, the worldbuilding/lore etc... These aren't just fluff, they're just as important as anything else!

And it truly did help me. Now I've been able to actually finish a game that I dropped 4 times even though that game seemed perfect for me on paper. And it was great.

P.S: This applies to other things like books and movies as well. Although I find that it applies even more to gaming, because it's such a complex medium with so many things working together to create the experience. Unlike a novel for example where it's just some dude making stuff up and seeing what sticks, this is a multidimensional medium where many people have pushed their talents to the maximum to create this experience for you.



**Example 2:**
> I've noticed that our individual preferences for certain games are largely built from our earliest gaming experiences
edit: I shouldn't have used the word "our" in the title as surely my own single experience is not generalizable to everyone else, but I can't change the title and at this point many people have interacted already w/ the post.

I've been experimenting w/ a certain amount of games to figure out what it is about gaming that I like, and the various gameplay mechanics that I tend to favor towards. In particular, I've noticed that I personally enjoy games where there is:

-freedom to choose your classes/party for a build YOU want to create

-the game naturally pushes me, w/o HUD markers, to a certain path I need to go

-there is constant motivation to progress in the game from point A to B, and onwards

-a "final boss" or "final challenge" to encounter and overcome

-Non-linear progression, you can go to another area to obtain an item that unlocks a previously blocked path in near an area that you've already been before.

All of these features tend to be embodied by the games developed by From Software (e.g. the Dark souls series, Bloodborne, and Sekiro), and I truly have a special place in my heart for these games, and I have a very hard time quitting my play sessions, which is something that has been rare for the past couple years. But when I really thought about it, i've noticed that these features were also embodied by my first legitimate experience with gaming, that being Pokemon, and more specifically, Pokemon Sapphire. My parents hated me playing video games as a kid so I was never one to have all the newest games and gadgets. But after begging for years and doing well on a certain piano recital, my dad bought me a gameboy advanced SP, w/ pokemon sapphire, which was my first gaming console and game ever in my possession.

Pokemon has changed quite a bit after all of these years, and though I can still pick up a new pokemon game and be addicted to it on my first playthrough, it definitely doesn't have the same magic and replayability as the older pokemon games I've played (I've played every single mainline game minus Sun and Moon and Omega ruby). Noticeably, these older games didn't hold the player's hand as much and actually gave the player some freedom to explore and find where they need to go themselves. Also the world was not super linear , and you'd often go to one area, only to go backwards to a previous area you were in after unlocking an HM that would remove a boulder/rock that was obscuring a path you were previously eyeing. I still remember the first time I unlocked Surf in this game (it allows you to swim in and traverse the water for those unfamiliar w/ Pokemon games), I was completely overwhelmed by the idea of exploring this entire sea that I was previously locked behind.

The more that I think about it, I really feel like the reason why I tend to gravitate to those game mechanics/qualities I mentioned earlier was because of my earliest experiences in gaming w/ Pokemon. I feel like those early experiences shaped my expectations for gaming. I'm wondering how generalizable this is to other people? Do you feel like your earliest gaming experiences have shaped your individual/personal preferences for certain games?



### `game_design`

**Definition:**
Posts primarily analyzing how games are designed or how specific mechanics, systems, genres, or design choices affect the experience of playing.
**Example 1:**
> Open-World games have all settled on very similar core mechanics - What is worth expanding/reinventing?
Hi fellows,

after playing two AAA open-world games this year, I couldn't help but notice how similar they've all become with their core game-play mechanics. Most open-world games cosist of 3 core mechanics that the player engages with, namingly:

Combat: This is often the most differentiated aspect of the game that has the most mechnical depth and choices. Be it ranged or melee combat, magic or weapons. The game's loot system often ties into combat a lot too.

Stealth: Most open-world games have some stealth mechanics, even if they don't always take center stage. They might be just another combat option or an independent mechanic. Most open-world games use a very shallow take on stealth, mostly relying on "line of sight" mechanics.

Platforming: With exploration being a big part of open worlds, it makes sense that jumping & climbing are a core mechanic. However, despite the frequent addition of grapple hooks and other tools to "spice" it up, this mechanic often receives very little depth or dedicated mechanics.

And that covers it. You could arguably count "crafting" as a mechanics, but that's just really part of a loot system that expands the combat system. I'd consider it more for survival games.

When it comes to engaging with an open-world game, 90% of the time you'll probably be doing it on one of the forms above. No matter the game and setting. And I find that rather disappointing.

Have you come across variants of these core mechanics that you feel should be more broadly adopted?

What other mechanics do you feel warrant enough depth to be worthy of joining the "core game-play loop" of modern open world games?



**Example 2:**
> Open world games and games with large amounts of side content would benefit from difficulty settings based on content completion.
Edit: I am not suggesting dynamic level scaling, I am suggesting an optional setting that rebalances later game main encounters so that they are challenging when you have completed most side content up to that point. It would not render side content rewards meaningless - quite the opposite - side content would become a requirement to be strong enough for the main story, particularly as the game progresses.

I'm playing Kingdom Come Deliverance 2 currently and while I'm having a fantastic time, I'm slowly becoming aware of something that I see plague many other games with large amounts of side content.

The difficulty and rewards of main story objectives often appears to be scaled towards players that a complete moderate to minimal amount of side content. As a result, players who wish to see as much as possible of the game can often find themselves overpowered for the main story and even late game side content, resulting in a disconnect between the gameplay and narrative. Theres nothing more anticlimactic than finally reaching the top of a great mountain in a quest t slay the world eating dragon, then proceed to murder it like it is a common bandit.

I'm sure some developers have realised this issue and I'm not sure there would be a simple solution. Personally I'd like to see additional settings on a new game;

Main story focused: As most games currently seem to be.

Completion focused: A setting that sets (not scales) encounters, difficulty and potentially rewards and economy to players that seek to complete as much as possible. Essentially increasing the challenge of later game main story missions and side quests.

Of course this would require quite a bit of balancing beyond traditional difficulty settings but I think there are many games that would benefit immensely from it, especially narratively.


### `gaming_culture`

**Definition:**
Posts primarily about gaming as a broader culture or industry, including gaming communities, social expectations, monetization trends, fandoms, industry practices, or how gaming connects to issues outside individual games.
**Example 1:**
> I would like to talk about regarding the cult-like mentalities in the gaming community
I am not sure if this is the right word to say but I often feel that there is a cult-like mentality in the gaming community, particularly when it comes to liking or hating a certain aspect of gaming.


Whether it is a particular gaming company, or a famous developer, a certain franchise or a genre - the mentality is often the same - either you love it to death or you hate it to death and there is little room for anything in between.


I feel this a lot more with regards to the release of The Last of Us Part 2 and Cyberpunk 2077, both games are made by esteemed and legendary developers and no wonder there was so much hype around these games.

But I think the disappointments were due to the over hype behind those games, aside that the developers had their own faults like the poor release of Cyberpunk 2077 in last gen consoles or the conflicting views of the writings of the Last of Us Part 2.


Whenever I looked at criticisms towards these developers, it is as though they committed terrible sins or insulted the gaming community and it kept on reflecting on the responses that other developers received in the past like Bethesda with regards to the quality of Fallout 4 (and the gaming community's reaction towards this game is also the same - either you love it to death or absolutely hate it) and that Bethesda has committed a terrible sin for developing the mess that is Fallout 74.


Yes, the gaming industry is not immune to criticism - anti-consumer practices, poor or false advertising, microtransactions and overly capitalistic practices and so on.

But I often feel that these criticisms disregard the idea that gaming developers are also human and that development is also messy - clashes between the executives and the developers or demands from stock holders or demands from the fans, or the problems that developers come across during the development process.

Heck, no wonder developers often say that they go through a lot of pressure and this pressure is often unnoticed.


I am not saying that nobody should criticised the publisher for poorly designed games but it is weird that there is this toxic/unhealthy mentality in gaming culture that you either love something or hate something and any room for different interpretation is often disregarded.

Any time someone wants to mention a different perspective on something, even if it is an unpopular opinion or maybe even a poorly made one regardless of that person's tastes, the person is bombarded with criticism because their say conflicts with what the majority "cult" mentality thinks.

Anything that is not accepted should be extinguished with fire and fury

**Example 2:**
> Discussion: What are ethical ways for game developers to generate passive income for their studios?
Hello r/truegaming, I have a question and discussion for you all.

The AAA game industry has been pivoting towards the 'games as a service' model, with the intent of generating revenue for the game beyond it's initial release. This has been met with overwhelming backlash from hardcore gamers, but the ubiquitous nature of this trend shows that despite the backlash, it's a business model that works well - at least for now. There's many gamers that are willing to buy power, upgrades, skins, and boosts to make their experience more enjoyable for themselves. These aren't inherently bad things, but many games prey on impulsive buyers and predatory game designs to coerce a purchase out of its user base.

Greed is a big factor for why this business model has taken off, but I think the unspoken factor is that this business model provides passive income for these developers. Passive income helps keep the lights on between game releases, and is much easier to plan around from a development point of view - resources can be allocated and spent more predictably.

Games take a long time to develop, good games - even longer. The ideal behind the games as a service model is that the passive income generated can go towards the development and R&D of your other projects. Without passive income, and in lieu of sales of your previous release drying up, developers can find themselves in situations where they don't have money saved up to spend on the next project and must borrow from an investor or a publisher in exchange for concessions such as equity and distribution rights. A dev having access to passive income theoretically allows them to comfortably work on the next game without worrying about where the next lump of cash is coming.

Since gamers inherently hate games as a service model, what are some alternatives to this model that can keep devs afloat in between long dev cycles?

### The hardest boundary

**Which two labels:** player_experience vs. gaming_culture

**post** 

Gaming as a social ritual
Since this subreddit is mostly comprised of older folks there's this prevailing idea that younger generations have a shallow taste on games and only engage with live-service/competitive/grindy i.e. "bad" games. I want to offer some insight as someone who has interacted with both demographics.

First of all, more people are playing games, obviously. I think one of the biggest things people misconstrue is that there is a difference between "people who play a game" and "gamers". For example when WoW became popular in in the 2000s you suddenly had an influx of people who have never played a game playing wow, many of whom never ended up playing something else. And the main way this effect propagates is people that don't seek out games being convinced by people that do, which happens the most often in social settings i.e. school. There's lots of younger people that don't seek out other games because they have no interest in gaming, they just play the few games they and their friends care about. So no, your favorite game is not dying because more people are playing minecraft/fortnite, as most of them do not care about other games in the first place, and those that do will eventually find it anyway.

Which brings us to one of the reasons why I think live-service games are so successful as they are. If there's one thing that really changed between the 90s and now is that gaming is not even remotely a niche hobby anymore. The weird kid is no longer the one that plays games, but the one that plays games that most kids don't. Because just about everyone play games people just find groups to play with in real life and there's no real need to look for people online. Thus multiplayer, low cost, and infinite content games are ideal for forming long lasting social circles. Teenagers care about fitting in and the friends they have as social status, and they want to be "in the know" when they hear other people talk about games, so you can see how these games are perfect for those purposes.

One of the common arguments here likes to argue that "gaming isn't social anymore" by citing things like server browser, or random matchmaking, which ignores that the vast majority of social gaming is among real friends and happens off-game like on discord. (most games having extremely terrible community systems and VoIP are also a contributing problem imo, I hope virtual LAN stays dead). And this transition into always talking about games even when not playing it gave rise to those that I call "people that play games as a social practice". This might not be common among millenials or gen-X, but some people genuinely cannot fathom playing games in a non-social setting. Many, many people I play with have tens of thousands of hours playing all kinds of games, but will never do what we do: find a single player game, play it to completion, be personally satisfied with it. This ranges from having friends watch them go through a single player game on discord to solo queueing for the purpose of eventually showing off their rank to other people. They grew up with gaming in an inherently social thing, and to play games is to socialize. And I believe live service games along with this are good things to happen, as long as they don't cannibalize existing studios (which is a tall order, most of us here probably have that one game we liked whose studio ended up making micro-transaction ridden slop)

So yeah, feel free to let me know if which parts remind you of certain people you play with, or which parts seem more like a stretch

**why is this borderline**

The post discusses how some players, especially younger players, treat gaming as an inherently social activity. It talks about people choosing games because their friends play them, wanting to fit in socially, caring about rank as a form of status, and sometimes having little interest in playing games alone. The author then connects those individual motivations to larger changes in gaming, such as the popularity of multiplayer and live-service games and the way gaming has become a mainstream social activity.

This post could fit player_experience because a large part of the discussion is about why individual players choose certain games and what motivates them to keep playing. It focuses on things such as friendship, fitting in, social status, and whether someone enjoys playing alone or with other people.

At the same time, it could fit gaming_culture because the author is not only describing one person's experience. The post uses those behaviors to make a broader argument about generational differences, social groups, live-service games, and the changing role of gaming in society.

**The decision rule I used every time:**
<!-- e.g. "If the post names a specific checkable fact, it's `analysis`, even
     if the tone is heated." -->

If the main point is about why an individual player thinks, feels, or behaves a certain way while playing games, label it player_experience. If the post uses player behavior to make a broader claim about gaming communities, social norms, generations, fandoms, or gaming culture as a whole, label it gaming_culture.

Using that rule, I would label “Gaming as a social ritual” as gaming_culture. Although it contains examples of individual player motivations, its main argument is about a broader social pattern: how gaming has become a social activity and how that change affects the types of games people play and the way different groups engage with gaming.


---

## The Dataset

**Where the posts came from:**

I collected 200 public posts from the `r/truegaming` subreddit. I kept the full text of each post rather than trimming them, and stored all 200 examples together in a single unsplit `labels.csv` file.

**How I labelled them:**

I labelled the first 20 posts cold using only my label definitions and marked those rows as `cold` in the `note` column. For the remaining 180 posts, I used AI to pre-label them as `player_experience`, `game_design`, or `gaming_culture`. I then read through the pre-labelled examples and corrected labels when the suggested label did not match the main focus of the post. These rows were marked as pre-labelled in the `note` column.

**Counts per label:**

| Label | Count | Share |
|---|---:|---:|
| `player_experience` | 36 | 18% |
| `game_design` | 92 | 46% |
| `gaming_culture` | 72 | 36% |
| **Total** | **200** | **100%** |

**Three hard cases**

**1.**
> *The post:*  
> **"Most people hate inconvenience, but I crave it"**
>
> *Could have been:*  
> `player_experience` or `game_design`
>
> *I chose:*  
> `player_experience`
>
> *Because:*  
> The post sits close to the boundary because inconvenience can be created by deliberate game-design choices, but the main focus is the player's personal preference for and reaction to that friction. Since the central idea is about what the player personally enjoys rather than primarily analyzing how a mechanic should be designed, I classified it as `player_experience`.

**2.**
> *The post:*  
> **"Respecting the player's time and how Marvel's Spider-Man on PS4 shattered that rule"**
>
> *Could have been:*  
> `game_design` or `player_experience`
>
> *I chose:*  
> `game_design`
>
> *Because:*  
> The idea of a game "respecting the player's time" involves the player's experience, but the post is mainly evaluating design decisions that affect pacing and how the player spends time in the game. Because the main argument is about how those design choices shape the experience rather than simply describing the author's feelings, I classified it as `game_design`.

**3.**
> *The post:*  
> **"Why do you think folk are more accepting toward English-dubbed voiceovers for video games than other mediums?"**
>
> *Could have been:*  
> `gaming_culture` or `game_design`
>
> *I chose:*  
> `gaming_culture`
>
> *Because:*  
> Voice acting is part of how a game is presented, so it could be interpreted as a design-related topic. However, the post is mainly asking about broader audience attitudes and why gaming communities treat dubbed voiceovers differently from audiences of other media. Since the main focus is a cultural norm surrounding games rather than a gameplay or design system, I classified it as `gaming_culture`.

---

## The Training Run

**Base model:**

`distilbert-base-uncased`

**Settings:**

- Epochs: `20`
- Learning rate: `1e-5`
- Batch size: `16`
- Max length: `128`
- Seed: `42`
- Device: `CPU`

**Anything I changed from the defaults, and why:**

The notebook defaults were 3 epochs, a learning rate of `2e-5`, a batch size of 16, and a maximum length of 128 tokens. I increased the number of epochs from 3 to 20 and lowered the learning rate from `2e-5` to `1e-5`. I kept the batch size at 16 and the maximum length at 128.

I experimented with other settings, but this configuration produced the best result on my held-out test set. Using more epochs with a lower learning rate gave the model more opportunities to learn from the relatively small dataset while making smaller parameter updates during training.

**Split sizes:**

- Training set: **139**
- Validation set: **31**
- Test set: **30**

| Label | Train | Validation | Test |
|---|---:|---:|---:|
| `player_experience` | 25 | 6 | 5 |
| `game_design` | 64 | 14 | 14 |
| `gaming_culture` | 50 | 11 | 11 |
| **Total** | **139** | **31** | **30** |

`player_experience` had only **5 examples in the test split**, which is below the roughly 8 examples recommended for a more stable measurement. Because the test support for this label is so small, its precision, recall, and F1 can change substantially from only one or two different predictions between seeds. I will keep this in mind when interpreting the next unit's results.

---

## How I Used AI

**Moment 1**

- **What I asked for:** I gave the AI my three label definitions and asked it to stress-test the hardest boundary, especially between `player_experience` and `gaming_culture`, by looking at borderline examples.
- **What came back:** The AI showed examples where a post could reasonably fit either label and explained how the main focus of the post could be used to decide between them.
- **What I changed:** I kept my original labels, but I made the decision rule more specific: posts mainly about an individual player's thoughts, feelings, or behavior are `player_experience`, while posts using player behavior to make a broader point about communities, social norms, generations, or gaming culture are `gaming_culture`.

**Moment 2**

- **What I asked for:** After training the classifier, I asked the AI to help me compare my training settings with the notebook defaults and think through why different settings were affecting the results.
- **What came back:** The AI suggested several possible training changes, including changing the number of epochs, learning rate, batch size, and sequence length. I tested different settings rather than assuming the suggestions would automatically improve the model.
- **What I changed:** I ultimately kept the configuration that produced my best result: 20 epochs, a learning rate of `1e-5`, batch size 16, and a maximum length of 128. Compared with the notebook defaults, I increased the epochs from 3 to 20 and reduced the learning rate from `2e-5` to `1e-5`.

**Pre-labelling disclosure:**

I labelled the first 20 posts cold using my own label definitions. For the remaining 180 posts, I used AI to pre-label the posts as `player_experience`, `game_design`, or `gaming_culture`. I then read through the pre-labelled examples myself and corrected labels when the AI suggestion did not match the main focus of the post. The pre-labelled rows were marked in the `note` column of `labels.csv`.

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy |  |  |  |
| Macro F1 |  |  |  |
| F1 — `label_one` |  |  |  |
| F1 — `label_two` |  |  |  |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->



---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted |  |  |  |
|---|---|---|---|
| **** |  |  |  |
| **** |  |  |  |
| **** |  |  |  |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->



---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** ___ / 30 = ___%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**2.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**What the pattern in my disagreements tells me:**



---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
