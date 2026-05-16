# LangAlong — Systems & Implementation Notes

| Field | Value |
|---|---|
| Version | 1 |
| Status | Completed Draft |
| Date | May 9, 2026 |
| Related GDD Version | 2 |

This document contains the mechanical detail behind systems described at a high level in the GDD. Numbers and specifics here are working values subject to change during development and playtesting.

---

## 1. Energy System

### 1.1 Energy Scale

Energy goes from 0 to 100.

### 1.2 Starting Energy

Unless the player has a better bed and gets a full loaf from the Baker, player energy maxes at 75. Having both of those results in energy at 100.

### 1.3 Automatic Time-Based Depletion

| Time | Energy Lost |
|---|---|
| 9am | 20 |
| 12pm | 20 |
| 3pm | 20 |
| 6pm | 15 |

### 1.4 Activity-Based Depletion

| Activity | Energy Cost | Notes |
|---|---|---|
| Farming | No cost | |
| Town ↔ Shore travel | 2 | Small penalty for a bit more realism |
| NPC interaction — first visit | 5 if "Come Back Later", otherwise 10 | |
| NPC interaction — second visit, same NPC | 5 no matter the result | Total of 10 for two visits |
| NPC interaction — third visit+, same NPC | No cost | No conversation thus no cost |

### 1.5 Running Out of Energy

When energy reaches 20, the player character states they feel tired. When energy reaches (or goes under) zero, the player states they feel sleepy, goes immediately home to bed, and sleeps a few seconds before the next day starts.

### 1.6 Restoring Energy

> **Note:** Better bed plus full loaf is required for visiting the NPC that opens at 6pm.

| Source | Energy Restored | Notes |
|---|---|---|
| Sleep — rough bed | 25 | Energy upon waking up |
| Sleep — better bed | 50 | Energy upon waking up |
| Bread crusts | 15 | |
| Half loaf | 30 | |
| Full loaf | 50 | |

---

## 2. Opinion System

### 2.1 NPC Opinion Scale

NPC opinion works on a scale from 0 to 2. Once an NPC reaches opinion score of 2, it locks at that level.

### 2.2 Gaining Opinion Points

| Player Action | Points Gained |
|---|---|
| Full sentence, no backspacing | 1 point up to maximum |
| Full sentence, with backspacing | 0.5 points up to 1.5 |
| Partial sentence / keyword only | 0 points |
| Wrong answer | 0 points |

### 2.3 Maximum Opinion Special Rule

If the player attempts to maximize NPC opinion from 1.5 to 2 but continues to use backspace in their answer, the NPC gives an appropriate reward for that type of answer, but opinion does not reach maximum. Then the Nurse Intervention Rule takes effect.

### 2.4 Nurse Intervention Rule

If the player attempts a full sentence three times and gets the same word wrong (e.g. trying to guess a particle by brute force), after leaving the NPC, a cutscene will play where the Nurse walks up to the player to say she's heard the player was having trouble, and points out the correct sentence. This both interrupts an attempt to brute force the answer and helps progress the game forward.

If the player attempts a complete sentence to maximize NPC opinion but backspaces, similar to above, a cutscene will play where the Nurse says she's heard the player having trouble and advises the player to think about the sentence before putting it in. This aids in progressing the story.

---

## 3. NPC Interaction Rules

### 3.1 Daily Interaction Limit

If the player interacts with an NPC and answers, it is considered a full NPC interaction and the player may not attempt again until the next day.

If the player interacts with an NPC and then clicks "Come Back Later", the player is permitted to talk to the NPC one more time that day. Upon returning, the "Come Back Later" option is replaced with a "Give Up" option.

Upon a second visit to the NPC, the player must either answer or "Give Up." The player may not attempt another answer with the NPC until the next day.

### 3.2 Escalating Energy Cost

See section 1.4 for energy depletion.

### 3.3 Sentence Evaluation

Minimum requirement for NPC action is a keyword associated with the NPC, e.g. "bread" for the Baker.

If the player submits a complete correct answer but has to use backspace to correct their answer, they get 0.5 opinion points and a lesser reward.

If the player submits a complete correct answer without using backspace, they get 1 opinion point and a full reward.

### 3.4 Backspace Tracking

There is a backspace button available in the UI, so if it is clicked at least once while the player puts together an answer, it counts.

---

## 4. NPC Schedules

| NPC | Opens | Closes |
|---|---|---|
| Baker | 6am | 12pm |
| Nurse | 9am | 10pm |
| Clothier | 12pm | 6pm |
| Carpenter (1st half of game) | 2pm | 6pm |
| Carpenter (2nd half of game) | 6pm | 10pm |
| Seed Store | 9am | 6pm |
| Produce Store | 9am | 3pm |

---

## 5. Food System

### 5.1 Bread

| Baker Interaction Result | Bread Received |
|---|---|
| No keyword | Bread crusts |
| Keyword only | Bread crusts |
| Partial sentence | Half loaf |
| Full sentence, with backspace | Half loaf |
| Full sentence, no backspace | Full loaf |

### 5.2 Farming

- **Seed acquisition:** Get seeds from Seed Store
- **Growth time:** Two days. No need for water or tilling soil — just plant them by looking at the plant box at the house on the beach and clicking the interact button. Seeds are tracked in inventory as a boolean (has / has no seeds).
- **Harvest:** Simply click the interact button when facing the crop to add it to inventory.
- **Sale to Produce Store:** If you talk to the Produce Store NPC with crop in inventory, the NPC will talk to you.

---

## 6. Bridge System

### 6.1 Visual Progress Trigger

Each time an NPC opinion maxes out (except for the last one), there is a cutscene where we see the bridge progress. Once the last NPC is maxed out, there is a special cutscene including the Nurse to take the player to the bridge.

### 6.2 Bridge Builder Unlock Condition

All NPCs must have maximum opinion for the Bridge Builder to request materials, which marks the second half of the game.

### 6.3 Bridge Completion Condition

After the Bridge Builder requests materials to finish the bridge, the player must get them from each NPC through the Fetch Quest System (Section 7). Once all items are collected, the player returns to the Bridge Builder, then delivers the items with a Capstone Sentence that lists all the items. See section 6.4 for Capstone Sentence Rules.

### 6.4 Capstone Sentence Rules

The capstone sentence should be a comprehensive exercise of sentence rules learned throughout the game. The sentence lists each item for the bridge, and no backspacing is allowed. If the player hits backspace or clicks "Give Up", the Bridge Builder dismisses the player claiming they can't understand them. The player may try again, but each attempt does take energy for NPC interaction.

As a specific language example, for Japanese, many different sentence particles should be used in the capstone sentence.

---

## 7. Fetch Quest System

### 7.1 Fetch Quest Rules

- When visiting the bridge, the Bridge Builder tells the player (in the island language) that they need certain items, and the town people can help.
- The guide book has the bridge material nouns added.
- The player must visit each NPC to ask if they have a bridge item.
- The NPC says they need an item themselves, which is a fetch quest item.
- The player gets the fetch quest item either from another NPC or from somewhere in the village (undetermined).
- The player returns to the NPC to say they have the fetch quest item.
- The NPC then gives the player a bridge item or tells them where it is.
- When finding either a fetch quest item or bridge item in the town, the player goes to the location and clicks the interact button.
- Open question: how an interaction with an NPC that has a fetch quest item happens. See section 9.
- Several new sentences are required for the fetch quest part of the game:
  - Bridge Builder: "I need these items to finish the bridge: x, y, z. The town people can help."
  - Player (to NPC): "Do you have a bridge item?" *(a generic sentence the player uses with each NPC to avoid making the player ask for each piece individually)*
  - Player (to Nurse): "Do you need anything?"
  - NPC: "I have [bridge item], but can you get [fetch quest item] for me first?"
  - Player: "I have [fetch quest item] for you."
  - NPC that has bridge item: "Thank you! Here is [bridge item]."
  - NPC that knows where bridge item is: "Thank you! You can find [bridge item] at [location]."

### 7.2 Item Collection & Delivery

Fetch quest items and bridge items are simple boolean "player has it / player does not have it" settings. The player may collect all of them at once or deliver as they go. However, all bridge items must be collected before talking to the Bridge Builder NPC to turn them in.

---

## 8. Day Cycle

### 8.1 Clock Rate

Initially the clock rate should equal one minute for one hour of game time, or one game minute passing every second.

When interacting with an NPC, the game clock should pause.

### 8.2 Day Schedule

| Event | Time | Notes |
|---|---|---|
| Day starts | 6am | |
| First energy drop | 9am | |
| Second energy drop | 12pm | |
| Third energy drop | 3pm | |
| Evening window opens | 6pm | Requires full energy |
| Day ends | Midnight or player sleeps | |

### 8.3 What Resets Each Day

- Baker has food
- Crops progress
- Starting player energy based on type of bed
- Clock starts at 6am
- "Come Back Later" option available for all NPCs
- NPC interaction limits reset

---

## 9. Open Questions

- When an NPC has a fetch quest item, should the player have to ask for the item or does the NPC just give the item upon first contact with the player during the day?
- How are interactions with the Baker NPC handled in the second half of the game, where interaction with the Baker is required for bread as well as fetch quests?

---

*LangAlong · Systems & Implementation Notes · v1 · 2026*  
