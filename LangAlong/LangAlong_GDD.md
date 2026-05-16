# LangAlong — Game Design Document

> **Design Principle:** LangAlong teaches players to form complete sentences in a foreign language by thinking about assembling the sentence correctly before saying it, as one would do in real life.

| Field | Value |
|---|---|
| Version | 2 |
| Status | Concept Draft |
| Date | May 7, 2026 |

---

## 1. Overview

This game is intended to help people form complete sentences in a foreign language by putting the player in a village where the player must learn the local language to progress.

### 1.1 Scope

This documents a demo game for mobile or web with one town for the player to progress through. This document covers main points of information for that first town.

### 1.2 Core Design Principle

The intention is to teach the player to think about forming complete sentences as if they were going to say the sentence to a native speaker. The author had difficulty forming sentences in Japanese with sentence particles, and that need drove the idea for this game. This game differs from games like DuoLingo — which gives the player a small set of language tiles to choose from — and uses a larger set that makes it more difficult to "brute force" the answer.

---

## 2. Target Audience

This game is intended for teens and adults that want to learn forming sentences in a language foreign to them. This game allows the player to role-play as if they were in a village and had to form complete sentences during everyday life. By building a foreign language sentence in their head, they are practicing for real life situations where they would need to do this.

---

## 3. Setting & Story

### 3.1 World

The game is set in the 1800s on an island with small towns and enough technology for carpentry, baking, and so on. Town shops include a baker, clothier, seed store, clinic, carpenter, and so on.

### 3.2 Player Character

The player is a shipwreck survivor that washes ashore on an island. Initially, there is a cutscene where the nurse from the clinic is there when the player wakes, and starts speaking in the island's language. The player tries speaking to the nurse, who realizes the different language, and then switches to the player's language.

### 3.3 Opening

The nurse guides the player to an abandoned house on the shore to stay at, which has minimal comfort. The player sleeps to recover. The nurse stops by in the morning with a book explaining some things about the local language, and points out the word for "bread" and tells the player to visit the baker for food. The player is moved to the baker in town and the conversation starts. The UI helps the player this one time by pointing at the word for "bread" and the "Say" button to show the player how the speech mechanic works.

---

## 4. Core Mechanic

### 4.1 What Does the Player Actually Do?

The player must get items and services from the town using words, and the more complete the sentence, the better the reward.

### 4.2 How Does It Work?

The main interaction loop is talking with an NPC, where the NPC asks a question in the foreign language, and the player is presented with word tiles in the foreign language, including several generic and wrong words and sentence particles. The player clicks the tiles to form a sentence, making corrections if needed, then clicking "Say" to present the sentence to the NPC. The player also has a "Come Back Later" or "Give Up" button in case they don't feel like they can answer the question. Coming back later allows the player to reference notes to answer properly. Giving up has the same effect as speaking with the NPC. The baker will give some bread crusts, but for all other purposes, the NPC cannot be spoken to again until the next day.

### 4.3 What Makes It Different?

The main differentiator is encouraging the player to think in complete sentences in the target language. DuoLingo uses tiles for words, but only supplies words in the sentence plus a couple of incorrect words. This game is intended to have lots of incorrect words to prevent brute-forcing correct answers. The goal is to have the player think of the complete sentence, then type it without error to obtain a full reward.

### 4.4 Variations on NPC Sentence Wording

To prevent rote memorization of responses and add variety, an NPC will vary the subject of their prompt to the player over repeated interactions. The player will be required to use a similar answer but geared toward the new subject. For some languages the change will be minimal, but other languages may require more support for the player such as additions to the guide the Nurse provides. Exact mechanics undetermined.

For example, the Baker starts with "Would you like some bread?" and changes to "Would you like some soup?" plus other apt variations.

To ensure the player does not see and immediately click on a new tile in the word tile pool, the word bank for the NPC should include at least some of the subject variations every time.

---

## 5. Game Loop

### 5.1 Short Loop (minute to minute)

The player goes to NPCs to get goods or services from them. The NPC asks a question. If the player simply says the key word for that NPC (e.g. "bread" for the baker), they get minimal help from the NPC. The best result comes from a complete sentence with no corrections.

Encouraging the player to make a complete sentence without mistakes promotes thinking about the sentence before answering, which is a core desired outcome of the game.

### 5.2 Medium Loop (day to day)

The player goes to each NPC to get goods or services. NPCs have varying schedules during the day, and the player has a finite amount of energy per day. At least one NPC requires full energy as that NPC is not available until near the end of the day.

The player is encouraged to increase NPC opinion of them to advance the game. When interacting with an NPC, the player sees an opinion scale with the NPC. With a successful sentence, the opinion scale increases toward a maximum score. Once that maximum score is reached, a cutscene occurs highlighting new progress on a bridge being built to get to the next town.

There's a small mechanic where the player must grow seeds into produce to talk to the Produce Store NPC. The player takes seeds from the seed store to grow over a couple of days, then the player gives the produce to the Produce NPC to advance that NPC's opinion.

### 5.3 Long Loop (overall progression)

The first half of play for a town is maximizing all NPC opinions to get the bridge to a near-completed state. Once all opinions are at maximum, a cutscene occurs where the nurse walks up to the player and, using the player's native language, indicates the bridge builder wants to talk to the player.

The second half of play occurs when the bridge builder specifies items needed for the bridge, and that the townspeople should be able to help.

When the player talks to the NPCs asking for a bridge item, the NPC asks for a favor, either talking to another NPC or getting an item from the town that's obvious and in plain sight. Once that is done, the player returns to the NPC and gets a bridge item. However, the bridge items cannot be returned without having all of them. Once all have been obtained, the player goes to the bridge builder and must compose a "capstone" sentence listing all the items. The sentence must be complete with no backspacing. Once the player is able to cross the bridge to the next town, the demo ends.

---

## 6. Characters & NPCs

**All NPCs:**
- Communicate in the target language only (foreign language to the player), except the nurse
- Ask the player a question that requires a sentence response in the target language
- Show a native language prompt (player's native language) on the input screen so the player knows what they should say
- Have a response timer in the second half of the game, mimicking a social situation where a person does not wait that long for a response
- Allow one conversation attempt per day; the player can delay the response only once per day with a "Come Back Later" option to return to the NPC later
- Each NPC requires multiple conversations across a few days to increase opinion to maximum to progress story; the contents of the conversations must be determined in a natural conversation manner, whether the player gets something from the conversation or not

---

### Baker
- **Role:** Gives player bread when asked for
- **Personality:** Pretty friendly and understanding
- **What the player needs from them:** Bread for energy to do things around town
- **What they need from the player:** To give the player bread, the player must give them a complete sentence
- **Special mechanic or rule:** Sells out of bread after being asked, no matter the outcome. Player at least gets bread crusts to continue the day. In the second half of the game, the first daily interaction is for bread, and a second interaction is required for a bridge item.

### Clothier
- **Role:** Gives player town-native clothing when asked
- **Personality:** Kind but quiet, somewhat understanding
- **What the player needs from them:** Town-native clothing to talk to the seed store manager
- **What they need from the player:** A polite request using a word from the dictionary given to the player
- **Special mechanic or rule:** Accessible early in game sequence

### Carpenter
- **Role:** Builds better bed for player when asked
- **Personality:** Most taciturn NPC, least understanding, requires complete sentences with no backspaces
- **What the player needs from them:** Better bed for more energy
- **Special mechanic or rule:** Store must be open long enough for a player with good energy (successful bread sentence) to reach, so the player can get a better bed for more energy

### Nurse
- **Role:** Safety net for player, helping them by speaking the player's language
- **Personality:** Very friendly, helpful, supportive; player's safety net for learning language
- **What the player needs from them:** Help getting started in the game, help with difficulty creating sentences for NPCs
- **Special mechanic or rule:**
  - Gives player vocabulary book for reference at start of game
  - Assists player if they repeatedly fail to talk to an NPC; if a player tries a sentence three times with a mistake, a cutscene occurs where the Nurse walks up and offers advice to help
  - Notifies player of bridge builder needing items
  - Second half of the game, the player is required to ask the Nurse for a bridge item without prompting

### Seed Store Manager
- **Role:** Give seeds to player to farm for produce
- **Personality:** Guarded against unknown people
- **What the player needs from them:** Seeds for growing produce, which is used to unlock the Produce Store Manager NPC
- **Special mechanic or rule:** Does not talk to player unless player has gotten clothes from the Clothier, thus relaxing the Seed Store Manager's guard

### Produce Store Manager
- **Role:** Undetermined for now
- **Personality:** Undetermined for now
- **What they need from the player:** One piece of produce grown from seeds to increase opinion. In the second half of the game (bridge items), gives the player something (undetermined) as a result of selling produce.
- **Special mechanic or rule:** Player must give produce to interact with this NPC with a sentence similar to "I have [produce] for you to sell." If no produce when talking to NPC in first half of game, says something like "Hello, come back when you have produce to sell."

### Bridge Builder
- **Role:** Builds bridge to next game area (town)
- **Personality:** Very fussy, only accepts complete sentences
- **What the player needs from them:** Access to the next game area (town)
- **What they need from the player:** After player improves all NPCs' opinion to maximum, requests player get bridge building materials from NPCs
- **Special mechanic or rule:** Only talks about bridge being built until he needs bridge materials. Only accepts bridge materials all at once and with a proper complete sentence.

### Evening NPC *(undetermined)*
- **Role & Personality:** One of the above NPCs
- **Special mechanic or rule:** Only open late in the day, thus requiring full energy to visit

---

## 7. Progression System

### 7.1 How Does the Player Advance?

#### 7.1.1 First Half of Game
- Give correct sentence to NPC to increase opinion
- Some NPCs will give items that unlock other NPCs
- One NPC is only reachable with full energy as they are open late at night
- Increase one NPC's opinion to maximum to advance bridge progress
- Increase all NPC opinions to maximum to start second half of game

#### 7.1.2 Second Half of Game
- Player must get bridge building items from each NPC
- Note that some NPCs (particularly the Baker) require two interactions to get the bridge item; the first interaction is for the item the NPC gives the player, like bread
- Each NPC asks for an item that is either easily found in town or with another NPC
- For the Nurse, the player must ask if the Nurse needs anything; all other NPCs freely talk about what they need
- Player must fetch the item or ask the target NPC for the item the other NPC wants
- Finishing the fetch quest for an NPC gets an item for the bridge
- Must turn in all bridge items at once
- Must turn in bridge items with a complete sentence with no backspaces
- When all bridge items are turned in, cutscene plays to cross bridge and end demo

### 7.2 Rewards

- If the player says a complete sentence but needs to backspace, the NPC gives a pleased reaction and there's a mild reward sound effect.
- If the player says a complete sentence with no backspacing, the NPC appears very pleased and there's a better reward sound effect.
- When the player maximizes an NPC's opinion, the player gets a cutscene where they see progress being made on the bridge.
- When the first NPC's opinion is maximized, the Nurse visits the player in an immediate cutscene to compliment them on their progress.
- When all NPC opinions are maximum, a cutscene has the nurse visit the player and compliment them on their language progress. The Nurse then shows the player to the bridge that is close to completion.
- When an NPC fetch quest (second half of the game) is completed, the same pleased reaction for a complete sentence with no backspacing is given, but a slightly better sound effect is given.
- When all bridge items are gathered and turned in to the bridge builder, a cutscene plays where the player is told to come back the next day. The game cuts to the next day where the player is walking into town where balloons are tied to shop fronts, and everyone is at the completed bridge waving. Then the player is given control to finish crossing the bridge.

### 7.3 Consequences

- Player progression in the game slows with incorrect sentences or where player backspaces before saying a sentence.
- With one interaction with an NPC per day (plus one "Come Back Later" action), they must repeat the interaction the next day.
- There is a small cutscene of sleeping during the night which takes a few seconds, so the player knows there is a small time penalty for getting things wrong.
- If the player doesn't give a complete sentence to an NPC, they get a "tepid" response with no sound effect.
- If the player runs out of energy during the day, they are forced to go to bed, again resulting in a cutscene of a few seconds as a small time penalty.
- If the player attempts to brute force getting a sentence right, after 3 failures there is a cutscene where the nurse walks up to the player and talks to them about hearing about their struggle, and as a help, points out the right way to finish the sentence.

---

## 8. Platform, Navigation, and Presentation

### Platform

The initial game concept is for mobile, but can be translated to desktop and console.

### Movement & Navigation

In movement mode, the player can move in 4 directions and has an interact button for talking to NPCs or interacting with whatever is in front of the player.

In NPC interaction mode, the player has one screen with the NPC and their question, and a second screen with the question, the expected response in the player's native language, a blank for the answer, and several language tiles. The player uses the movement keys to switch between tiles and screens, and the interact button to click on a tile. There is a "Say" button to submit the sentence to the NPC. There is also a "backspace" button to erase the previous word, and a "Come Back Later" or "Give Up" button (starts as Come Back, then it's Give Up) where the player does not submit a sentence.

### Key UI Elements

Time of day and player energy remaining are always visible. Indications of what keys do are also visible: main action button is "interact" and pause button is "pause/menu."

The pause menu has a reference for the language in the form of a book given to the player, as well as a "Save & Quit" option.

### Visual Direction

The game's visual style can be similar to Stardew Valley; the graphics are low definition for less memory consumption. The visual design for NPCs should be lighthearted and like a comic. The outfits for each store should be consistent across towns, but some variation on color, style, and person wearing the outfit is fine. All NPCs have a distinct appearance given the store / business they manage.

### Audio Direction

Background sound should be similar to being on an island with ocean wave sounds faint in town and more prominent on the shore. Music should be relaxing and not prominent. NPCs talk in native language alongside the text visible to the player. When player "Say"s a sentence, we hear a native speaker saying the sentence, even if wrong.

---

## 9. Out of Scope

This document does not include market research for demand for this kind of game. It does not include wireframes or specific design regarding the user interface. It only covers a demo game that leads across a completed bridge to the end of the game. It does not include any support for online validation of player accounts.

---

*LangAlong · Game Design Document · v2 · 2026*  
