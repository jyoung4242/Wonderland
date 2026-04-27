# Wonderland — Game Design Document

### Version 0.1 — Working Draft

---

## Table of Contents

1. [Core Vision](#1-core-vision)
2. [Core Pillars](#2-core-pillars)
3. [Narrative Foundation](#3-narrative-foundation)
4. [World Design](#4-world-design)
5. [Movement & Traversal Kit](#5-movement--traversal-kit)
6. [Input Map](#6-input-map)
7. [Enemy Design & Loot](#7-enemy-design--loot)
8. [Card Combat System](#8-card-combat-system)
9. [The 52 Card Identity Map](#9-the-52-card-identity-map)
10. [Deckbuilding Progression](#10-deckbuilding-progression)
11. [Ante System](#11-ante-system)
12. [Relics](#12-relics)
13. [Open Items & Next Steps](#13-open-items--next-steps)

---

## 1. Core Vision

**"A precision platforming metroidvania where movement skill builds tactical card power, and boss fights become high-stakes wagers of
your own deck."**

A fish-out-of-water human pursues their partner Alice into a corrupted Wonderland ruled by the Queen of Hearts. The world is structured
around the mythology of a standard 52-card deck. Movement mastery, tactical card combat, and a risk-driven ante system combine into a
single cohesive experience.

Core inspirations:

- **Hollow Knight** — world scale, environmental storytelling, narrative depth
- **Ninja Gaiden** — traversal feel, movement as identity
- **Celeste** — control responsiveness, precision
- **Slay the Spire** — deckbuilding depth
- **Alice in Wonderland (American McGee interpretation)** — tone, unsettling surrealism

---

## 2. Core Pillars

### Pillar 1 — Platforming Exploration

Moment-to-moment gameplay is movement-based. Tight, fluid traversal through a large interconnected world. New movement abilities unlock
exploration in a Metroidvania structure. The movement fantasy is ninja-style — fast, fluid, OP-feeling by late game.

### Pillar 2 — Card-Based Boss Combat

Boss encounters shift into structured turn-based card combat. A standard 52-card deck provides all card identities. Combat is defined
by hand management, combo sequencing, and reading boss behavior.

### Pillar 3 — Deckbuilding Progression

Players build a personalized deck over the course of the game. The deck persists between encounters and evolves through exploration,
crafting, combat, and risk.

### Pillar 4 — Risk & Consequence

The ante system creates genuine stakes. Cards and currency are wagered in optional and mandatory encounters. Permanent card loss means
every decision carries weight.

---

## 3. Narrative Foundation

### Setting

Wonderland is a corrupted card kingdom — a fever dream that is internally consistent but never explained. Its logic is treated as
normal by its inhabitants. The player character never fully adjusts. Things are wrong in ways that cannot be named.

### The Player Character

A purely human partner — Alice's real-world companion. No magic, no destiny, no prior knowledge of Wonderland. They know about
Wonderland only through Alice's stories and never entirely believed them. They are a fish out of water in every sense.

Their competence is entirely real-world:

- Athletic, physically capable (justifies traversal kit)
- Emotionally driven — love is the only motivation
- Interprets Wonderland through confusion and stubbornness

Their identity is revealed through the world rather than self-description. NPCs reference them by a name Alice gave them. The player
learns who this person is through how Wonderland remembers Alice talking about them.

### Alice

Not a passive MacGuffin. Alice is present throughout the world:

- **Echoes and memories** — environmental fragments of her first visit, now corrupted
- **NPC memory** — the resistance knew her; some revere her, some blame her
- **Brief contact moments** — once per biome, the player finds a way to communicate with Alice. She is surviving, observing, feeding
  information.
- **Retroactive agency** — late game reveals Alice had been trying to find a way back on her own. She knew something was coming.

### The Queen of Hearts

Not a straightforward tyrant. The Queen captured Alice again not purely for revenge but because Alice is the only person who ever truly
_saw_ Wonderland — and the Queen needs to be seen. Loneliness and wounded pride drive her as much as power. Her tragedy becomes legible
across the journey.

### Tone

Beautiful, melancholic, genuinely unsettling. The game does not wink. It does not acknowledge how strange it is. It simply is.
Sustained unreality without irony.

---

## 4. World Design

### Scale & Structure

Hollow Knight scale. Large, handcrafted, interconnected map. Distinct biomes with strong visual identity, lore, atmosphere, and
resident NPC factions. Environmental storytelling is load-bearing. Cutscenes are used sparingly — for boss introductions, major
world-state changes, key NPC deaths or revelations. Day-to-day narrative lives in dialogue and environmental detail.

### Biome Progression — Narrative Arc

The four biomes map to the four suits and tell a story of escalating power and corruption. Difficulty and traversal kit requirements
scale with biome order.

---

#### Clubs — The Forge Depths _(Entry Biome)_

**Theme:** The working class of the card kingdom. Brutal, industrial, forgotten soldiers and laborers. **Narrative:** What was
sacrificed to build this kingdom. **Visual:** Industrial decay, forge fires, heavy machinery gone wrong. **Enemy types:** Armored,
physical, slow but powerful. **Movement challenge:** Momentum-based traversal, heavy platforming. **Card pool bias:** Clubs cards
dominate drops. **Boss:** Jack of Clubs (regional lieutenant). Drops Jack of Clubs signature card + one relic.

---

#### Diamonds — The Arcane Archive _(Second Biome)_

**Theme:** The aristocracy and scholars. Wealthy, controlled, complicit. **Narrative:** Knowledge as complicity. **Visual:** Floating
ruins, crystalline structures, magical interference fields. **Enemy types:** Projectile-based, area control, evasive. **Movement
challenge:** Precision traversal through magical hazard fields. **Card pool bias:** Diamonds cards dominate drops. **Boss:** Jack of
Diamonds (regional lieutenant). Drops Jack of Diamonds signature card + one relic.

---

#### Spades — The Shadow Canopy _(Third Biome)_

**Theme:** Underground resistance, assassins, exiles. Those who refused to serve. **Narrative:** Rebellion and sacrifice. **Visual:**
Dark forest or underground network. Fast, layered, built for movement. **Enemy types:** Fast, evasive, precision-focused. **Movement
challenge:** Full traversal kit required. Designed for the ninja fantasy peak. **NPC faction:** The resistance — allies, the people who
knew Alice. **Card pool bias:** Spades cards dominate drops. **Boss:** Jack of Spades (regional lieutenant). Drops Jack of Spades
signature card + one relic.

---

#### Hearts — The Bleeding Sanctum _(Final Biome)_

**Theme:** The seat of power. The Queen's domain. **Narrative:** Devotion twisted into tyranny. **Visual:** Cathedral-like, beautiful
and horrifying. Pulsing, organic, devotional. **Enemy types:** All suit types represented. The Queen's full court. **Movement
challenge:** Mastery of the complete kit required. **Card pool bias:** Hearts cards dominate drops. **Final Boss:** The Queen of
Hearts. Multi-phase. Each phase references the suits conquered.

---

### Safe Zones

The Hollow Knight bench equivalent. Distributed throughout each biome. The primary meaningful locations in the world outside of boss
arenas and NPC locations. All deck management and relic management happens here.

**Safe zone facilities:**

- **The Deck Table** — add/remove cards from active deck, view full collection
- **The Forge** — variant upgrades, card crafting from fragments
- **The Merchant** — not at every safe zone; rotating stock that updates after each boss defeat
- **The Vault** — protected storage for cards immune to ante loss (starts at 5 slots, expandable)

### The Graveyard

Removed from design. Not needed.

---

## 5. Movement & Traversal Kit

### Design Principles

1. Base kit feels complete — unlocks feel transformative, not corrective.
2. Every ability has both a traversal use and a combat use.
3. Ability acquisition matches the fish-out-of-water arc — desperation early, mastery late.

### The Flow Meter

Hidden connective tissue linking movement and combat.

Chaining movement abilities without touching the ground builds the flow meter through **input variety** — not repetition. Pressing the
same input repeatedly does not build flow. Creative chaining does.

**States:** Grounded → Moving → Flowing → Apex

- Controller rumble increases subtly as flow builds
- Distinct short pulse at Apex state — unmistakable once learned
- Taking a hit drops the meter one state (not to zero)
- **Entering a boss arena at Apex:** draw 6 cards on first hand instead of 5
- **Post-boss reset:** flow resets to Moving state — partial reward for traversal, fresh start for exploration

### Full Traversal Kit — By Acquisition Phase

#### Base Kit _(available from start)_

| Ability                    | Traversal Use                     | Combat Use                                   |
| -------------------------- | --------------------------------- | -------------------------------------------- |
| Run / directional movement | Standard navigation               | Approach, retreat, spacing                   |
| Short dash                 | Gap crossing, dodge               | Iframe window (mid-dash only), repositioning |
| Single jump                | Basic vertical                    | Jump cancel, aerial spacing                  |
| Basic melee attack         | Breaking environmental objects    | Primary damage                               |
| Wall slide                 | Slow descents, brief wall contact | Stall, bait enemy attacks                    |

**Dash specifics:**

- Duration: ~0.15-0.2 seconds
- Distance: ~2.5 character lengths
- Iframes: middle portion only, not startup or recovery
- No cooldown; air dash limited to once per airborne (resets on landing, wall contact, or grapple)
- Dash can cancel into jump at any point; jump cannot cancel into dash until landing

---

#### Phase 1 Unlocks _(Clubs biome — survival adaptation)_

| Ability     | Traversal Use                     | Combat Use                             |
| ----------- | --------------------------------- | -------------------------------------- |
| Wall jump   | Vertical shafts, chained climbing | Escape pressure, aerial repositioning  |
| Double jump | Wider gaps, height access         | Extend aerial combos, dodge follow-ups |
| Ground slam | Break weak floors                 | AoE stagger on landing                 |

---

#### Phase 2 Unlocks _(Diamonds biome — tool acquisition)_

| Ability      | Traversal Use                              | Combat Use                            |
| ------------ | ------------------------------------------ | ------------------------------------- |
| Grapple hook | Point-to-point traversal, swing initiation | Pull enemies or self to enemies       |
| Air dash     | Directional aerial movement                | Iframe in air, extend juggle combos   |
| Parry        | —                                          | Precise timing window, counter system |

**Grapple specifics:**

- Aim-assisted toward valid anchor points — no free-aim
- **Tap:** zip to point, arrive with momentum burst
- **Hold:** swing on rope, release to launch with arc momentum
- Swing physics are slightly physics-generous — Wonderland favors movement
- Enemy grapple: lightweight enemies pulled to player; heavy enemies pull player to them
- **Option B targeting:** if airborne → auto-targets; if grounded → opens aim mode

---

#### Phase 3 Unlocks _(Spades biome — mastery)_

| Ability     | Traversal Use                       | Combat Use                                                     |
| ----------- | ----------------------------------- | -------------------------------------------------------------- |
| Rope swing  | Momentum arc traversal, wide chasms | Pendulum kick, aerial slam                                     |
| Wall run    | Sustained horizontal wall traversal | Wall-run contact with enemy deals light hit and bounces player |
| Shadow step | Short blink through thin barriers   | Phase through attacks, teleport strike                         |

**Wall run specifics:**

- Requires minimum horizontal velocity to initiate — cannot start from standing
- Duration: ~1.5-2 seconds before gravity reasserts
- Extendable by chaining wall jump → back into wall run
- Subtle camera tilt during wall run

_Note: "Thin barriers" for shadow step requires explicit technical definition before implementation._

---

#### Phase 4 Unlocks _(Hearts biome — transcendence)_

| Ability         | Traversal Use                       | Combat Use                             |
| --------------- | ----------------------------------- | -------------------------------------- |
| Full wall climb | Any surface, any direction          | Ceiling ambush, repositioning anywhere |
| Momentum surge  | Burst speed, chain into any ability | Gap closer, devastating entry strike   |

---

## 6. Input Map

### Design Principle

Modal input — same buttons, different outputs depending on context. The _logic_ of each button stays consistent across all modes so
muscle memory transfers.

### Face Buttons — The Action Layer

| Button       | Traversal      | World Combat       | Card Combat                  |
| ------------ | -------------- | ------------------ | ---------------------------- |
| A / Cross    | Jump           | Jump / launcher    | Confirm / play card          |
| B / Circle   | Dash           | Dash / dodge       | Cancel / back                |
| X / Square   | Attack         | Primary attack     | Inspect card                 |
| Y / Triangle | Context action | Special / finisher | Arm reaction card / end turn |

**Logic consistency:** A = upward intention. B = evasion/exit. X = offensive action. Y = significant commitment.

### Triggers & Bumpers — The Modifier Layer

| Input   | Traversal                         | World Combat               | Card Combat                    |
| ------- | --------------------------------- | -------------------------- | ------------------------------ |
| RT / R2 | Hold: aim grapple / release: fire | Hold: target lock          | Submit combo group             |
| LT / L2 | Hold: wall run mode               | Hold: block / parry stance | Hold: enter card grouping mode |
| RB / R1 | Ground slam                       | Heavy attack               | Draw indicator (passive)       |
| LB / L1 | —                                 | Swap attack stance         | Discard selected card          |

### Sticks & D-Pad

| Input            | Function                             |
| ---------------- | ------------------------------------ |
| Left stick       | Movement / card hand navigation      |
| Right stick      | Camera / aim                         |
| L3               | Sprint toggle                        |
| R3               | Recenter camera / target cycle       |
| D-pad Up         | Quick heal / consumable              |
| D-pad Down       | Observe (environmental storytelling) |
| D-pad Left/Right | Cycle equipped relics                |

### Modal Transitions

**Traversal → World Combat:** No transition. Same mode. Combat and movement are one continuous expression.

**World Combat → Boss Card Combat:** Brief cinematic beat (0.5s). Arena spatially shifts into card battlefield. Input map changes.
Subtle UI confirmation. No tutorial pop-up.

**Boss Card Combat → Traversal:** Victory. Spatial shift reverses. Movement returns before victory animation completes. Preserves
momentum. Feels triumphant.

---

## 7. Enemy Design & Loot

### Enemy Role

Regular enemies are not progression gates. They make the world feel alive and dangerous and reward skillful traversal. Skilled players
route around or dispatch efficiently. Enemy encounters are optional depth — completionists engage for lore drops and fragment drops.

### Enemy Suit Alignment

Enemies within each biome are suit-aligned. Their behavior reflects their suit identity:

- **Clubs enemies:** Physical, armored, slow but hard-hitting
- **Diamonds enemies:** Ranged, evasive, area control
- **Spades enemies:** Fast, precision-based, flanking
- **Hearts enemies:** Sustaining, tanky, sacrifice-based attacks

### Loot Drop System

Three drop categories. All drops are optional depth — avoiding enemies is always valid.

#### Currency

- Common drop, auto-collects on proximity
- Named thematically (TBD — not "gold")
- Feeds into: card merchants, buyback NPC, surplus trade NPC, forge costs

#### Health Drops

- Pulse of light, absorbed immediately with visual flourish
- Hearts-zone enemies drop health more frequently — reinforces biome identity

#### Card Fragments

- Distinct card-shaped sliver, suit-colored, hovers briefly before collection
- Suit fragments drop from suit-aligned biome enemies
- Rank fragments are rarer, tied to enemy difficulty
- Fragments combine at the Forge to craft base cards

**Fragment crafting produces base cards only.** Variants are never craftable — they require the upgrade path.

**Crafting costs (approximate):**

| Card Rank       | Suit Fragments | Rank Fragments |
| --------------- | -------------- | -------------- |
| 2-5             | 2              | 1              |
| 6-10            | 3              | 1              |
| Jack/Queen/King | 4              | 2              |
| Ace             | 5              | 3              |

**Boss defeat world-state change:** After a boss is defeated, enemies in that biome have a chance to drop boss-infused fragments — a
new fragment quality that feeds into boss-infused variant upgrades.

---

## 8. Card Combat System

### Overview

Boss encounters shift into structured turn-based card combat. The player brings a personally constructed deck and plays from it against
a boss with health, armor, weakness systems, and telegraphed actions.

### The Combat Round

```
DRAW 5 → PLANNING PHASE → COMBO SUBMISSION(S) → INDIVIDUAL PLAYS → BOSS PHASE → DRAW 5
```

#### Draw Phase

- Player draws exactly 5 cards from their deck
- If deck is empty, discard pile reshuffles into deck automatically
- Apex flow state on entry grants 6 cards on the first draw only
- New cards cannot be drawn until all 5 are played — the hand must be fully committed before drawing again

#### Planning Phase

- Full tactical pause — time is stopped
- Player sees full hand, boss telegraph, and current board state
- **Combo helper UI** highlights valid combo groupings automatically
- Player groups cards into: Combo Group 1, Combo Group 2 (if available), Individual pile
- Boss telegraph shows: suit symbol (action type), rank indicator (power level), status icons

#### Card Grouping Input

- Navigate hand with left stick
- **Hold LT** to enter grouping mode
- In grouping mode: left stick selects/deselects cards into active group; flashing animation on currently active card
- **RT** submits the active group as a combo (if valid combo exists)
- **B** cancels grouping, returns to navigation
- Combo helper validates group in real time — invalid groups show clearly before submission

#### Combo Submission

- Up to 2 combo submissions per turn
- Each submission resolves simultaneously as one event — all cards in the group fire together
- After both combo submissions (if applicable), remaining cards play individually in player-chosen order
- **High Card scenario:** if no valid combos exist in hand, all 5 cards play individually. This is a valid and expected game state.

#### Reaction Cards

- Reaction cards are armed during the play phase using **Y button**
- Arming a reaction card counts as one of the 5 card plays for the turn
- Armed reaction triggers automatically during Boss Phase when its condition is met
- **If a reaction card is the last card remaining in hand:** it is auto-armed without requiring Y input, and applies to the current
  Boss Phase
- Only one reaction card can be armed per turn

#### Boss Phase

- Boss executes its telegraphed action
- Armed reaction card triggers if applicable
- Boss then telegraphs its next action (visible before next draw)

---

### Combo System

Combo evaluation checks the cards submitted in a group simultaneously. The group is classified by the highest qualifying combo tier.
Individual card effects always fire — the combo bonus is on top.

#### Combo Hierarchy (highest to lowest)

| Combo           | Requirement                    | Bonus Effect                                                             |
| --------------- | ------------------------------ | ------------------------------------------------------------------------ |
| Straight Flush  | 5 consecutive ranks, same suit | Fate-altering ultimate — suit-specific, phase-skip potential             |
| Four of a Kind  | 4 matching ranks               | Boss-breaking — destroy one armor layer, stagger 2 rounds                |
| Full House      | 3 of a kind + pair             | Transformation state — all cards upgraded for 2 rounds                   |
| Flush           | 4+ same suit                   | Suit ultimate ability fires (see Suit Ultimates)                         |
| Straight        | 5 consecutive ranks            | Momentum Chain — each subsequent individual card this turn costs nothing |
| Three of a Kind | 3 matching ranks               | Stagger — skip boss's next telegraphed action                            |
| Two Pair        | 2 different pairs              | Efficiency — draw hand contains 6 cards next round                       |
| Pair            | 2 matching ranks               | Second card's primary effect triggers twice                              |
| High Card       | No combo                       | Individual card effects only — no bonus                                  |

**Ace rank fluidity:** For combo evaluation, Aces count as rank 1 or rank 14 — whichever completes the best qualifying combo. The game
auto-evaluates and displays the optimal interpretation. The Ace's suit effect still resolves normally — rank fluidity is for combo
classification only. Visual indicator shows whether Ace is playing high or low before submission.

**Full House choice:** A Full House hand can be submitted as one Full House (higher bonus) or split into Two of a Kind + Pair as two
separate submissions (lower combined bonus). The game shows both options. Splitting is always the weaker play — the Full House bonus is
intentionally superior to reward recognition.

#### Suit Ultimate Abilities — Flush Trigger

**Hearts Flush — Sanguine Surge** Restore HP equal to total damage dealt this round. Rewards high-damage Hearts decks that sacrifice to
deal damage.

**Clubs Flush — Shatterforce** All boss armor reduced one tier this round. Every subsequent Strike card deals bonus damage equal to
boss's current stagger value.

**Spades Flush — Phantom Step** Player becomes untargetable for entire Boss Phase this round. Draw 3 cards on next draw (hand of 8,
play all 8 next turn).

**Diamonds Flush — Arcane Dominion** Take control of boss's telegraphed action — redirect back at boss or nullify entirely. Next
individual card played costs zero resources.

#### Joker Rules

Jokers are not in the player's deck. They are visitors — a low probability replacement for any drawn card.

- **Probability:** ~4% per card drawn (~18.5% chance of at least one Joker per 5-card hand)
- After hand resolves, Joker disappears — never enters discard or deck
- Red and Black Joker appear at equal probability when a Joker does appear

**Red Joker — The Fool** Counts as any rank and suit for combo evaluation. Automatically completes the best possible combo the other
cards are closest to forming. No individual card effect — its entire value is combo completion.

If Red Joker could complete two different combos, **the player chooses** which interpretation to use. The UI shows both options.

**Black Joker — The Wild** Fixed effect: all combo bonuses this hand are upgraded one tier. Individual effect: reveal and copy the
boss's next telegraphed action, turn it against them.

**Joker Event** (Black Joker upgrades a Four of a Kind):

- Boss staggered for 2 rounds
- All boss armor stripped
- Player takes a second full turn immediately (draw 5, play full hand, before boss phase)
- Visual: screen distortion, card imagery fragments — Wonderland acknowledges the event

---

### Boss Structure

Every boss has three structural layers:

#### Layer 1 — Armor

Flat damage reduction on all incoming effects. Represented as a shield icon with a number. Broken by: Four of a Kind combo, specific
Clubs cards, accumulated stagger. Once broken per phase, stays broken.

#### Layer 2 — Weakness System

| Boss Affinity | Weak To  | Resistant To |
| ------------- | -------- | ------------ |
| Clubs boss    | Diamonds | Spades       |
| Diamonds boss | Clubs    | Hearts       |
| Spades boss   | Hearts   | Diamonds     |
| Hearts boss   | Spades   | Hearts       |

Weakness: 1.5× effect. Resistance: 0.5× effect.

#### Layer 3 — Phase Gates

Bosses have phase thresholds at 75%, 50%, and 25% HP.

At each threshold:

- Boss behavior pattern changes
- New armor layer may regenerate
- Telegraph actions become more complex
- A **phase card** is added to player's discard pile — a powerful single-use card that only exists for this fight, carrying the boss's
  own power

Phase cards are the mechanical and narrative climax of each boss fight — using the boss's own power against them.

### Boss Telegraph System

Boss intent displayed as a card symbol above them during Planning Phase:

- Suit symbol = action type
- Rank indicator = power level (number = moderate, face = significant, Ace = unknown/dangerous)
- Status icons = additional effects (poison, armor gain, stagger)

---

## 9. The 52 Card Identity Map

All card effects reflect simultaneous combo resolution — "next card played" language has been reframed to work within the grouped
submission model.

### Clubs — Force / Strike

| Card  | Type   | Effect                                                                                  |
| ----- | ------ | --------------------------------------------------------------------------------------- |
| 2     | Strike | Light hit. Builds stagger meter.                                                        |
| 3     | Strike | Light hit. Builds stagger meter.                                                        |
| 4     | Strike | Light hit + small armor pierce.                                                         |
| 5     | Strike | Light hit. If stagger meter is half full, deal bonus damage.                            |
| 6     | Strike | Medium hit.                                                                             |
| 7     | Strike | Medium hit. If submitted in a combo, stagger meter fills faster.                        |
| 8     | Strike | Medium hit + brief stun.                                                                |
| 9     | Strike | Heavy hit. Applies stagger.                                                             |
| 10    | Strike | Heavy hit. Bonus damage if boss is already staggered.                                   |
| Jack  | Surge  | If submitted in a combo, the highest-damage Strike card in that combo fires twice.      |
| Queen | Strike | Cleave — damages boss and destroys one active boss buff.                                |
| King  | Strike | Finisher — bonus damage scales with boss's current stagger value.                       |
| Ace   | Strike | Deals damage equal to total number of cards submitted this turn (combos + individuals). |

---

### Spades — Mobility / Precision

| Card  | Type     | Effect                                                                                                                           |
| ----- | -------- | -------------------------------------------------------------------------------------------------------------------------------- |
| 2     | Guard    | Dodge — reduce incoming boss damage by 30% this Boss Phase.                                                                      |
| 3     | Guard    | Dodge — reduce incoming boss damage by 30% this Boss Phase.                                                                      |
| 4     | Guard    | Precision dodge — negate a small hit entirely if boss telegraph is a low-rank action.                                            |
| 5     | Shift    | Reposition — discard one card from hand, the next draw phase draws one extra card.                                               |
| 6     | Shift    | Reposition — discard one card from hand, the next draw phase draws one extra card.                                               |
| 7     | Shift    | Scout — reveal the boss's action two rounds ahead instead of one.                                                                |
| 8     | Strike   | Precision strike — ignores armor entirely.                                                                                       |
| 9     | Strike   | Precision strike — ignores armor. Bonus damage if boss telegraph is a face card action.                                          |
| 10    | Strike   | Precision strike — ignores armor. If boss is staggered, deals critical damage.                                                   |
| Jack  | Surge    | If submitted in a combo, this card is a free rider — does not affect combo classification but its individual effect still fires. |
| Queen | Reaction | Vanish — arm this card to become untargetable this Boss Phase. Auto-arms if last card in hand.                                   |
| King  | Strike   | Execution — if boss is staggered, deal massive damage scaling with remaining boss HP missing.                                    |
| Ace   | Surge    | Copy the effect of any one other card submitted this turn. Player chooses which card to copy.                                    |

---

### Hearts — Sustain / Sacrifice

| Card  | Type   | Effect                                                                                             |
| ----- | ------ | -------------------------------------------------------------------------------------------------- |
| 2     | Mend   | Recover small HP.                                                                                  |
| 3     | Mend   | Recover small HP.                                                                                  |
| 4     | Mend   | Recover moderate HP. If submitted in combo, deal damage equal to HP recovered.                     |
| 5     | Mend   | Recover moderate HP. If submitted in combo, deal damage equal to HP recovered.                     |
| 6     | Guard  | Sustain — reduce all incoming boss damage this round by a flat amount.                             |
| 7     | Guard  | Sustain — reduce all incoming boss damage this round. If boss is a Hearts-type, reduction doubles. |
| 8     | Guard  | Barrier — absorb the next source of boss damage entirely (up to a cap).                            |
| 9     | Mend   | Sacrifice — lose HP now. Next draw phase draws 6 cards instead of 5.                               |
| 10    | Mend   | Sacrifice — lose significant HP now. Next draw phase draws 7 cards instead of 5.                   |
| Jack  | Surge  | Lifesteal — the next Strike card submitted this turn heals for a portion of damage dealt.          |
| Queen | Mend   | Pulse — heal based on number of cards remaining in deck (rewards large deck builds).               |
| King  | Strike | Martyr — if player is below 25% HP, deal double damage this turn.                                  |
| Ace   | Surge  | Reset — shuffle discard pile back into deck immediately. Draw phase proceeds normally.             |

---

### Diamonds — Arcane / Control

| Card  | Type   | Effect                                                                                                           |
| ----- | ------ | ---------------------------------------------------------------------------------------------------------------- |
| 2     | Hex    | Apply Weaken — boss deals reduced damage next Boss Phase.                                                        |
| 3     | Hex    | Apply Weaken — boss deals reduced damage next Boss Phase.                                                        |
| 4     | Hex    | Apply Expose — boss takes +25% damage from the next hit this round.                                              |
| 5     | Hex    | Apply Slow — boss telegraph delay increases by one round.                                                        |
| 6     | Surge  | Amplify — if submitted in a combo, the highest-impact card in that combo has its effect enhanced by 50%.         |
| 7     | Surge  | Amplify — if submitted in a combo, the highest-impact card in that combo has its effect enhanced by 50%.         |
| 8     | Surge  | Double Amplify — if submitted in a combo, the two highest-impact cards both have their effects enhanced.         |
| 9     | Hex    | Manipulate — delay boss telegraph by one round. Boss must choose a new action.                                   |
| 10    | Hex    | Unravel — strip one boss buff. Deal damage equal to that buff's remaining duration in rounds.                    |
| Jack  | Surge  | Echo — if submitted in a combo, duplicate the effect of one other card in that combo. Player chooses which.      |
| Queen | Hex    | Dominate — copy one active boss buff and apply it to the player for two rounds.                                  |
| King  | Strike | Unravel — strip all boss buffs. Deal damage equal to total buffs removed × a multiplier.                         |
| Ace   | Surge  | Reclaim — choose any card from the discard pile. Play it as a bonus card this turn (does not count toward hand). |

---

### Reaction Card Summary

Reaction cards arm during the play phase (Y button) and trigger automatically during Boss Phase.

| Card           | Reaction Effect                                            |
| -------------- | ---------------------------------------------------------- |
| Spades 2-4     | Dodge — reduce incoming damage                             |
| Spades Queen   | Vanish — full damage negation this Boss Phase              |
| Hearts 6-8     | Absorb — convert a portion of incoming damage to healing   |
| Diamonds 9     | Redirect — delay or reroute boss action                    |
| Diamonds Queen | Counter-Dominate — nullify one boss buff before it applies |

---

## 10. Deckbuilding Progression

### Starting Deck

At game start the player builds a 10-card starter deck from a restricted pool.

**Starting pool:** All 2s, 3s, 4s, and 5s from all four suits (16 cards total). **Rules:** Choose exactly 10 cards. Must include at
least 2 different suits. No variants available.

The starting choice communicates archetypes without explaining them. Heavy Clubs = aggression. Heavy Spades = mobility. Mixed =
flexibility. All are valid.

### The Collection

The player owns two distinct inventories:

**The Collection** — everything ever acquired. Permanent. Cards in the Collection are available for deck building.

**The Active Deck** — the currently equipped subset (20-40 cards). Modified only at safe zones.

### Deck Rules

- **Minimum deck size:** 20 cards
- **Maximum deck size:** 40 cards
- **Same card limit per active deck:** Maximum 4 copies of any single card identity
- **Variant copy limit:** Base and variant versions of the same card count toward the same 4-copy limit
- **No hard cap on collection size** — unlimited duplicates can be owned
- **Ace limit:** Maximum 2 Aces total in any active deck

### Duplicate Strategy

Duplicates are a deliberate strategy. Three copies of the same rank in a 20-card deck means that rank appears in ~75% of all 5-card
draws. Stacking duplicates trades variety for reliability.

Duplicates serve multiple roles:

- Deck redundancy — guaranteed combo availability
- Loss insurance — losing one copy is survivable
- Ante fodder — sacrificing surplus copies in risk encounters
- Rare vault keys — duplicate-gated ante encounters

### Card Acquisition Sources

Ranked by frequency (most to least common):

1. **Fragment Crafting** — enemy drops feed the forge. Produces base cards only.
2. **Exploration Pickups** — hidden cards in the world. Always base cards. Reward curiosity.
3. **NPC Purchases** — rotating merchant stock. Currency-based.
4. **Boss Rewards** — guaranteed complete face card or Ace on boss defeat. Always significant.
5. **Ante Rewards** — variants and rare cards. High risk, high value.
6. **NPC Questlines** — unique variant cards unavailable elsewhere. Rarest category.

### Variant System

Variants are permanent upgrades that consume the base card. Once a base card is upgraded, it is replaced by the variant. New base
copies can be acquired and upgraded separately. Each copy tracks upgrade progress independently.

#### Tier 1 — Gilded Variant

_Visual: Gold border_ Enhanced base effect. No downside.

**Upgrade condition:** Use the base card in a set number of boss fights. Usage tracked per copy.

| Rank            | Boss Fights Required |
| --------------- | -------------------- |
| 2-5             | 10                   |
| 6-10            | 7                    |
| Jack/Queen/King | 5                    |
| Ace             | 3                    |

#### Tier 2 — Corrupted Variant

_Visual: Dark cracked border_ Enhanced effect with a meaningful downside. Higher ceiling, real cost.

**Upgrade condition:** Ante the base card in a specific risk encounter and win. The corruption happens through the ante system — the
card comes back changed.

Examples:

- Corrupted 9♣ — double damage but player takes 20% recoil
- Corrupted Q♥ — heals based on deck size but removes 3 cards temporarily each use
- Corrupted J♠ — free rider effect extended but next combo submission is skipped

#### Tier 3 — Boss-Infused Variant

_Visual: Boss sigil replaces suit symbol_ Entirely new effects beyond base card identity. Collection crown jewels.

**Upgrade condition:** Defeat the boss. Return to their arena and complete a post-boss mastery challenge. The challenge is designed
around the boss's combat mechanics — proof of mastery.

Boss-infused variants are the only cards with effects entirely outside the base card's identity.

### Surplus Trade NPC

Accepts excess duplicates in exchange for targeted cards:

| Offer                         | Receive                                        |
| ----------------------------- | ---------------------------------------------- |
| 4× low rank duplicates (2-5)  | 1× random mid rank card (6-10)                 |
| 3× mid rank duplicates (6-10) | 1× random face card                            |
| 2× face card duplicates       | 1× specific face card of chosen suit           |
| 1× Ace duplicate              | 1× card from merchant's curated personal stock |

### Deck Building Arc

| Biome    | Deck State                                               | Focus                                        |
| -------- | -------------------------------------------------------- | -------------------------------------------- |
| Clubs    | 10 starter cards, growing slowly                         | Learning the starter identity                |
| Diamonds | Mid-rank cards arriving, first Gilded variants available | Finding the deck's second dimension          |
| Spades   | Broad collection, enough for genuine slot decisions      | Committing to an archetype                   |
| Hearts   | Full collection, trim toward 20-25 for endgame           | Curation — cutting good cards for great ones |

**Design principle:** The deck is never quite right. Early it is too small. Mid game it grows faster than it can be optimized. Late
game the player cuts cards they like for cards they need. Chasing the perfect deck — always improving, never complete until the final
boss — is the deckbuilder's core fantasy.

---

## 11. Ante System

### Philosophy

**You are wagering something you earned, against something you want, with no safety net.**

Permanent card loss on defeat. Loss hurts proportionally to how many copies the player owns:

- Only copy lost → significant sting, strategic gap
- One of two copies lost → noticeable, deck weakened
- One of three copies lost → minor setback, deck mostly intact

### Two Ante Categories

#### Mandatory Antes — Toll Gates

Required for progression. Cannot advance without paying.

**Locations:**

- Biome transition gates (all four transitions)
- Specific boss access doors
- One narrative moment in the Hearts biome (see below)

**Rules:**

- Game always shows full cost before commitment
- Player chooses which cards or currency to risk — never randomized forced loss
- Player can always step back and prepare before committing

**Mandatory minimum requirements:**

| Transition        | Minimum Ante                      |
| ----------------- | --------------------------------- |
| Opening → Clubs   | 50 currency (tutorial ante)       |
| Clubs → Diamonds  | 1 card (any rank) + 100 currency  |
| Diamonds → Spades | 1 card (rank 6+) + 200 currency   |
| Spades → Hearts   | 1 face card or Ace + 500 currency |

**Hearts biome transition as narrative scene:** The mandatory ante is not a menu prompt. It is an encounter with a Hearts court
representative who demands the wager directly. The ante becomes a story scene. Same mechanical cost, completely different emotional
register.

**Progress-blocking safety valve:** If a player cannot meet a mandatory ante requirement (all qualifying cards have been lost),
alternatives are available:

- Economy path — a large currency payment substitutes for the card requirement
- NPC quest path — complete a specific questline to reclaim a qualifying card or satisfy the requirement through service
- These alternatives are intentionally harder or more time-consuming than simply meeting the ante requirement

#### Optional Antes — Gamble Rooms

Voluntary. Announced clearly through distinctive visual and audio design. Three types:

**The Duel Room** Combat encounter against a powerful unique enemy.

- Ante cards and/or currency before entering
- Win: reward scales with ante value
- Lose: anted items permanently lost, exit at low HP

**The Table** Non-combat gambling with a Wonderland NPC dealer.

- Currency primary, cards optional
- Each dealer has a unique game mechanic
- Skill element exists but luck is genuinely present
- Odds and win conditions always shown before committing

**The Double Down Table** (special Table variant):

- Ante 2× of any card
- Dealer matches with 2× of a card from their stock
- Winner takes all four cards
- Only way to gain two copies of a specific card simultaneously

**The Cursed Vault** Locked room with reward visible through the door. Fixed ante cost displayed on the door. No combat, no chance —
pay the price, take the reward.

Some Cursed Vaults require duplicate cards:

- Requirement displayed: e.g., _"ANTE REQUIRED: 2× 9♣ (base or variant)"_
- Requires owning and sacrificing both copies
- Reward tier scales with rarity of duplicate demanded
- Creates a specific farming goal — players know exactly what to accumulate

### What Can Be Anted

**Cards:** Any card from active deck or collection. Vaulted cards cannot be anted.

**Currency:** Always available as a component. Cannot fully replace card antes in mandatory transitions.

**Ante value by card type:**

| Card Type            | Ante Value |
| -------------------- | ---------- |
| Base 2-5             | Low        |
| Base 6-10            | Moderate   |
| Base Face Card       | High       |
| Base Ace             | Very High  |
| Gilded Variant       | High+      |
| Corrupted Variant    | Very High  |
| Boss-Infused Variant | Extreme    |

### Suit-Aligned Rewards

The suit of anted cards biases the reward pool:

| Anted Suit  | Reward Pool Bias                                         |
| ----------- | -------------------------------------------------------- |
| Hearts      | Healing items, sustain relics, Hearts variants           |
| Clubs       | Combat upgrades, damage relics, Clubs variants           |
| Spades      | Mobility relics, exploration rewards, Spades variants    |
| Diamonds    | Rare cards, control relics, Diamonds variants            |
| Mixed suits | Cross-suit rewards unavailable through single-suit antes |

### Reward Tiers

| Ante Value | Reward                                                                                     |
| ---------- | ------------------------------------------------------------------------------------------ |
| Low        | Currency profit, base cards (common ranks), minor consumables                              |
| Moderate   | Significant currency profit, mid-rank cards, common relics, first Gilded variants          |
| High       | Rare base cards, face cards, uncommon relics, Corrupted variants                           |
| Very High  | Guaranteed face card or Ace, rare relics, Boss-Infused variants, unique questline triggers |
| Extreme    | Rarest game rewards, unique cards, permanent world-state change                            |

### Card Loss Systems

**The Vault** Safe zone facility. Protected storage immune to all ante loss. Cards in the Vault cannot be anted. Starts at 5 slots,
expandable through exploration.

**The Sacrifice System** At the safe zone Forge: sacrifice 3 copies of a rank to protect a fourth copy of that rank from permanent loss
for one ante encounter. Protection is temporary (one encounter) and the three sacrificed cards are gone. Used for pushing very high
antes on a specific irreplaceable card.

**The Buyback NPC** One per biome. Recovers one permanently lost base card per visit.

| Card Rank | Buyback Cost  |
| --------- | ------------- |
| 2-5       | 300 currency  |
| 6-10      | 600 currency  |
| Face Card | 1200 currency |
| Ace       | 2500 currency |

Variants cannot be recovered through buyback. A lost Corrupted or Boss-Infused variant is gone permanently.

---

## 12. Relics

### Philosophy

Relics modify the rules of the combat sequence. They never modify card effects directly.

- **Cards** define what each play does
- **Combos** define the bonus for playing cards together
- **Relics** define how the combat sequence behaves around those plays

This is a clean separation. Relics change the rules. Cards change the output.

### Relic Slots

Maximum 3 relics equipped simultaneously. Swapped only at safe zones alongside deck management.

### Combo Elevation Cap

No combination of relics can elevate a combo more than **two tiers above its base classification**. This cap applies regardless of how
many relics are stacked.

### Relic Catalog

#### Draw Phase Relics

**The Marked Deck** Once per fight, before the first draw, look at the top 8 cards of your deck and arrange them in any order.

**Bottom Feeder** When drawing a hand of 5, the bottom card of your deck is always included as the fifth draw.

**The Hungry Draw** If your discard pile has 15 or more cards in it, draw 6 instead of 5. The sixth card must be played individually —
it cannot be part of a combo submission.

**Mirror Draw** Once per fight, after seeing your hand but before playing any cards, swap your entire hand with the top 5 cards of your
deck.

**Suit Magnet** When drawing, if 3 or more cards of the same suit would be drawn, the fourth draw is always from that same suit if one
exists in the remaining deck.

---

#### Combo Evaluation Relics

**The Wild Standard** Joker probability increases from ~4% per card to ~8% per card.

**Broken Sequence** Straights can be evaluated with one rank gap — A-2-4-5-6 counts as a valid Straight.

**Suit Blindness** Flush evaluates on rank only — 4 cards of matching rank triggers Flush regardless of suit. When active, this
classification **replaces** Four of a Kind — the hand evaluates as a Flush only, not both. The player trades Four of a Kind bonus for
Flush bonus.

**The Escalator** Each combo submitted this round evaluates one tier higher than it qualifies for. Subject to the two-tier elevation
cap.

**Double Tap** When a Pair combo is submitted, it automatically evaluates as Two Pair — the second pair is phantom.

**The Patient Hand** If only one combo is submitted this round and all remaining cards play individually, that combo evaluates one tier
higher. Subject to the two-tier elevation cap.

---

#### Boss Phase Relics

**The Parry Clock** During Boss Phase a timing window appears. Successfully pressing confirm within the window reduces incoming damage
by 50%.

**Spite** When the boss deals damage to the player, 20% is reflected back to the boss.

**The Interrupt** Once per fight, completely negate one boss action before it resolves. Boss telegraph resets — they choose a new
action next round.

**Armor Reading** At the start of each Boss Phase, the exact damage value of the incoming boss action is revealed before it resolves.

**The Punisher** If the boss uses the same telegraphed action twice in a row, the second instance deals zero damage and the player
draws one card immediately on next draw phase.

---

#### Discard / Deck Cycle Relics

**The Remembering** The first card played from a freshly reshuffled deck is immediately copied to the discard pile — it effectively
plays twice across the cycle.

**Thin Blood** When your deck has 10 or fewer cards remaining before drawing, all combo bonuses this round deal 50% more effect.

**The Hoarder** Cards played individually (not as part of a combo) have a 25% chance of returning to hand instead of entering the
discard pile.

**Compost** When the discard pile reshuffles into the deck, one random card is temporarily removed from the deck for this fight only.
The removed card's suit determines a passive bonus for the remainder of the fight. The card returns after the fight.

**The Echo Chamber** The last combo submitted before a reshuffle is guaranteed as the first combo-eligible hand configuration after
reshuffle.

---

### Relic Acquisition

| Source         | Notes                                                              |
| -------------- | ------------------------------------------------------------------ |
| Exploration    | Hidden in significant world locations. Never random drops.         |
| Boss rewards   | One relic per boss. Thematically connected to boss's combat style. |
| Ante rewards   | High-value antes. Suit of anted cards biases relic phase type.     |
| NPC questlines | Rarest and most powerful relics. Unavailable elsewhere.            |

### Notable Relic Synergies

**Thin Blood + The Hungry Draw + Bottom Feeder** Play deep into deck cycle (Hungry Draw activates), grab guaranteed bottom card, hit
Thin Blood power window. Deliberate end-of-cycle power spike every fight.

**The Escalator + The Patient Hand** One combo per round evaluates two tiers higher (Patient Hand +1, Escalator +1). Pair becomes Full
House bonus. Requires restraint.

**Suit Magnet + Suit Blindness** Suit Magnet pushes toward mono-suit draws. Suit Blindness makes four matching ranks trigger Flush.
Together they push toward a specific hand state triggering Flush effects consistently.

---

## 13. Open Items & Next Steps

### Resolved Decisions (from consistency pass)

- ✅ Grouping input: LT to enter grouping mode, left stick to select, RT to submit
- ✅ Reaction card arming: Y button; auto-arms if last card in hand
- ✅ High Card scenario: documented as valid baseline turn
- ✅ Jack of Spades redesigned: free rider in combo
- ✅ Diamonds 6-8 redesigned: amplifies highest-impact card in combo
- ✅ Hearts 9-10 redesigned: next draw phase draws extra cards
- ✅ Variant upgrade consumes base card permanently
- ✅ Per-copy usage tracked independently
- ✅ Mandatory ante safety valve: economy or NPC quest alternatives
- ✅ Escalator cap: maximum two tier elevation
- ✅ Compost: card returns after fight
- ✅ Suit Blindness: replaces Four of a Kind classification, does not stack
- ✅ Flow meter post-boss: resets to Moving state
- ✅ Fragment crafting: base cards only
- ✅ Graveyard system: removed
- ✅ Hearts biome transition: narrative scene, not menu prompt

### Systems Not Yet Designed

- Enemy design (types, behaviors, suit-specific patterns)
- NPC roster and questline design
- Currency economy tuning
- Boss fight design (specific bosses beyond Jack of each suit)
- World map structure and interconnection
- Audio and visual design language
- UI/UX design beyond input mapping

### Key Prototyping Priorities

1. 5-card hand with full play-all commitment loop
2. Combo grouping UI with LT grouping mode
3. Combo detection across simultaneous submission
4. Pair bonus as first working combo
5. Dummy boss with telegraph system
6. Joker probability and Red Joker combo completion logic

---

_Document version 0.1 — Working Draft_ _Last updated: current session_ _Next session: enemy design, NPC roster, or boss fight
specifics_
