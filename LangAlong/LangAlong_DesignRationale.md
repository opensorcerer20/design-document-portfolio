# LangAlong — Design Rationale

| Field | Value |
|---|---|
| Version | 1 |
| Status | Completed Draft |
| Date | May 16, 2026 |
| Related GDD Version | 2 |

This document captures the reasoning behind key design decisions in LangAlong. Entries are added as decisions are made or revisited. Each entry is a standalone record — the goal is to explain not just what was decided but why, and what was considered along the way.

---

## Entry 1 — All bridge items must be turned in as a full set rather than piecemeal

**Decision:** The player must collect all bridge items, then tell the bridge builder the items they got in a single capstone sentence to advance over the bridge.

**Context:** Finishing the bridge is a big moment in the game progression.

**What was considered:** Turning in items as they were collected was considered, but writing a sentence for each item would be very repetitive.

**Why this choice:** This single turn-in is built up as the player collects bridge items, and the capstone sentence execution is a landmark moment for the player understanding and executing the language.

**Revisit if:** Players feel the quest is too long, the capstone sentence is too difficult, or the buildup does not have the desired effect.

---

## Entry 2 — Using many language tiles rather than more targeted answer tiles

**Decision:** When a player is given language tiles to form a sentence, many incorrect tiles are present, particularly sentence particles.

**Context:** This aids a central mechanic of the game: to force the player to construct a correct sentence from many possible words. Other language games have too few options, so guessing the answer is easy.

**What was considered:** Having the player type in the words rather than use word tiles was also considered.

**Why this choice:** Using tiles is more mobile-friendly and increases the pace of the game. It also allows providing similar but wrong answers, which forces the player to think about what the right answer is.

**Revisit if:** Aside from deciding between using tiles or text input, this is a core mechanic that shouldn't be changed.

---

## Entry 3 — At least one NPC only available late at night

**Decision:** At least one NPC is only available late at night, requiring full energy and energy conservation to last that long.

**Context:** This adds a bit of strategy around energy consumption by the player and adds incentive for bread and a better bed.

**What was considered:** No alternatives were considered.

**Why this choice:** This was a natural extension of the idea of NPCs having varying times they are open, and the waning energy mechanic contributed to this idea.

**Revisit if:** Players have difficulty figuring out how to reach this NPC.

---

## Entry 4 — Whether to allow opinion points to go down

**Decision:** Opinion points do not go down.

**Context:** While the idea of opinions degrading over time is good, when I reduced the opinion meter down to 2 points, I felt that losing opinion didn't serve any purpose.

**What was considered:** I considered having opinions go down if the player neglected an NPC, as well as having opinions go down after an initial maximum opinion was reached — e.g. reaching an opinion score of 3 locked the floor of that opinion, and every 2 days the opinion would drop half a point, while the player tried to increase the opinion to 5 to lock it in again.

**Why this choice:** With a smaller point requirement, deducting points didn't seem to serve a good purpose.

**Revisit if:** If the point system is increased in scope or the game is increased in scope, losing opinion points may serve a purpose.

---

## Entry 5 — NPC Sentence Variations

**Decision:** Have NPC conversations alter a noun occasionally in a way the player takes note of.

**Context:** For NPC sentences like "Would you like some bread?", the NPC alters the subject, and the game highlights the new word so the player takes notice — e.g. "bread", "croissant", "sandwich". The player then must use that word in their response.

**What was considered:** No other options considered.

**Why this choice:** This prevents rote memorization of answers, and adds some usage knowledge for altering sentences when the subject changes.

**Revisit if:** Players have trouble with additional vocabulary words being added.

---

## Entry 6 — Small penalty for use of backspace when responding

**Decision:** For completion of an objective, a full sentence without backspacing must be used.

**Context:** This was added to force the player to think about their next tile selection rather than mindlessly hitting tiles to answer.

**What was considered:** This was an add-on and no other options were considered.

**Why this choice:** There were two main reasons to add this. One, as stated, is to prevent the player from going through the game mindlessly by hitting tiles. Another is to encourage the player to form the sentence in their head before answering. This may parallel actual conversation in real life where you think about what you're going to say before you say it.

**Revisit if:** A better mechanic for encouraging thinking before answering is devised.

---

## Entry 7 — A 2-point opinion scale with 0.5-point steps

**Decision:** Use an opinion scale from 0 to 2 with advancements of either 0.5 points or 1 point.

**Context:** I needed an opinion scoring system that wasn't too long, and wanted to reward the player for answering correctly but reward more if they did so without backspacing.

**What was considered:** I considered more points and utilizing loss of opinion points, but for the former, I didn't want the game to be too repetitive, and for the latter, I felt it might complicate the game more than necessary.

**Why this choice:** I wanted a softer gate to encourage players to think about their answers, so I allow the player to get nearly to full opinion, but then require an answer without backspacing to complete the quest.

**Revisit if:** A better solution is found that lets the player have a decent number of iterations per mission and a reward for thoughtful correct answers.

---

## Entry 8 — Player energy drain mechanic

**Decision:** Player energy starts at a certain point, can be enhanced with bread, and degrades during the day. If energy reaches 0, the player goes to bed to start a new day.

**Context:** This adds a strategy element to the player planning their day. It also adds a natural gate for an NPC that is only available late in the day.

**What was considered:** No other options were considered.

**Why this choice:** I wanted the player to plan each day rather than just doing every NPC every day, which would be monotonous. It also gives reason for the player to get bread and a better bed to reach the evening NPC.

**Revisit if:** This mechanic is important to add variety and a real-life feel to the game, so I don't recommend changing it unless a better option presents itself.

---

## Entry 9 — Nurse intervention after 3 similar failures

**Decision:** Have the Nurse help the player if they have made a mistake on the same word 3 times.

**Context:** Assist the player when the game detects three mistakes on the same word.

**What was considered:** No other options were considered.

**Why this choice:** This mechanic does two things: it helps the player when they are not progressing, and helps interrupt an attempt to brute force an answer by trying every tile.

**Revisit if:** Players find the assistance to be invasive or uncalled for.

---

## Entry 10 — Nurse is the only bilingual NPC

**Decision:** The Nurse NPC is the only bilingual NPC.

**Context:** I wanted the player to have a softer introduction to allow less friction getting started in the game. It's a simple game story setup.

**What was considered:** I considered having more NPCs be bilingual or just having the player refer to a book for translations.

**Why this choice:** It made more sense for the island natives to only speak their own language, but I wanted a smoother introduction to the island for the player. And if the player washes up on the beach as a story setup, the Nurse tending to them makes sense, so I had the Nurse also speak the player's language.

**Revisit if:** There are significant changes to the plot of how the player gets to the island.

---

## Entry 11 — Player must prompt Nurse for fetch quest

**Decision:** While other NPCs respond to the question "do you have a bridge item?", the Nurse doesn't have one — thus the player must ask the Nurse if they need anything. Once that item is given to the Nurse, the NPC remembers where a bridge item is.

**Context:** This was added as a bit of variety and problem solving for the fetch quest part of the game. It encourages the player to come up with a question without prompting.

**What was considered:** No other options were considered.

**Why this choice:** This was a desire to have the player be more proactive in conversations.

**Revisit if:** A more apt event where the player initiates a conversation is devised.

---

*LangAlong · Design Rationale · v1 · 2026*  
