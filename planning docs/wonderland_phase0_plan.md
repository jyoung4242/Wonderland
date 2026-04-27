# Wonderland — Phase 0 Implementation Plan

### "Does the card combat feel good?"

**Goal:** Reach the fun gate — a playable card combat loop against a dummy boss — as fast as possible, with no throwaway code.

---

## Guiding Principles for This Phase

- **Nothing is a spike.** Every milestone produces code that lives in the real project.
- **Logic before polish.** Visuals are placeholder until the loop feels good. Don't decorate what you haven't validated.
- **Small sessions count.** Each milestone is scoped to be completable in 1–3 hours. Variable schedule is fine.
- **The fun gate is the finish line.** Phase 0 is done when you play a full hand against a boss and feel something.

---

## Project Setup

### Milestone 0 — Scaffold (1–2 hrs)

Stand up the Excalibur project with the conventions that will survive into the full game.

**Deliverables:**

- Excalibur project initialized (Vite + TypeScript)
- Folder structure established:
  ```
  src/
    actors/
    scenes/
    systems/
    data/
    ui/
  ```
- A single `CombatScene` as the entry point — this is where all Phase 0 work lives
- Placeholder background, no art required

**Done when:** `npm run dev` opens to a blank `CombatScene` with no errors.

---

## Milestone 1 — The Card Data Model (1–2 hrs)

Build the data layer that represents the deck. This is pure TypeScript — no Excalibur, no rendering.

**Deliverables:**

- `Card` type: `{ rank, suit, id }`
- `Suit` enum: `Clubs | Diamonds | Spades | Hearts | Joker`
- `Rank` enum: `Two` through `Ace`, plus `Joker`
- `buildStandardDeck()` — returns all 52 cards + 2 Jokers
- `shuffle(deck)` — Fisher-Yates, seeded via Excalibur's `Random`
- `DeckState` class:
  - `drawPile: Card[]`
  - `hand: Card[]`
  - `discardPile: Card[]`
  - `draw(n: number)` — moves top N cards to hand
  - `discardHand()` — moves hand to discard
  - `reshuffle()` — discard back to draw pile, reshuffled

**Done when:** You can run `buildStandardDeck()`, shuffle it, draw 5, and log the hand to console correctly.

> **Note:** No Joker special logic yet. Jokers are just cards in the deck at this stage.

---

## Milestone 2 — Hand Display (2–3 hrs)

Render the hand on screen. Placeholder card visuals only — colored rectangles with rank/suit text is fine.

**Deliverables:**

- `CardActor` — an Excalibur Actor that displays one card
  - Shows rank + suit as text
  - Color-coded by suit (any 4 colors)
  - Selected state: slight upward offset or border highlight
- `HandDisplay` — manages layout of up to 5 `CardActor`s in a horizontal row
  - Cards are evenly spaced, centered on screen bottom
  - Clicking/tapping a card toggles its selected state
- `CombatScene` draws 5 cards on scene start and renders them via `HandDisplay`

**Done when:** 5 cards appear on screen and you can click to select/deselect them.

---

## Milestone 3 — Grouping Mode (2–3 hrs)

Implement the LT grouping mechanic from the GDD. This is the core input pattern for combo submission.

**Deliverables:**

- Keyboard stand-in controls (gamepad comes later):
  - `G` key = enter/exit grouping mode
  - Click cards to add to group while in grouping mode
  - `Enter` = submit group
  - `Escape` = cancel grouping, clear selection
- `GroupState`:
  - `isGrouping: boolean`
  - `pendingGroup: Card[]`
  - `submittedGroups: Card[][]` — groups confirmed this round
- Visual grouping indicator: a bracket or highlight around grouped cards
- Cards not in any group are treated as individual plays on submit

**Done when:** You can group 2–3 cards, see them visually bracketed, submit, and log the submitted groups to console.

---

## Milestone 4 — Combo Detection (3–4 hrs)

The heart of the card combat system. Evaluate submitted groups against the combo table.

**Deliverables:**

- `ComboEvaluator` — pure function, no side effects:
  ```
  evaluate(cards: Card[]): ComboResult
  ```
- `ComboResult` type: `{ type: ComboType, tier: number, label: string }`
- `ComboType` enum — implement in order of complexity:
  1. `HighCard` — baseline, always valid
  2. `Pair` — 2 matching ranks
  3. `TwoPair` — 2 separate pairs
  4. `ThreeOfAKind`
  5. `Straight` — 5 sequential ranks
  6. `Flush` — 5 same suit
  7. `FullHouse` — Three of a Kind + Pair
  8. `FourOfAKind`
  9. `StraightFlush`
  10. `RoyalFlush`
- Each combo maps to a tier (1–10) for damage calculation later
- Log the result to screen after submission

**Done when:** You can submit any valid poker hand and see the correct combo name and tier displayed.

> **Defer:** Joker wildcard logic, Relic modifications, and the play-all commitment rule. Those come in Milestone 6.

---

## Milestone 5 — Dummy Boss (2–3 hrs)

Something to fight. No AI, no complexity — just enough boss structure to make the card combat feel purposeful.

**Deliverables:**

- `DummyBoss` Actor:
  - `maxHP: number` (e.g. 500)
  - `currentHP: number`
  - HP bar rendered above boss (rectangle, no art)
  - `takeDamage(amount: number)` — reduces HP, triggers visual flash
  - `telegraph()` — randomly selects one of 3 dummy actions and displays it as text:
    - "Incoming: 20 damage"
    - "Incoming: 40 damage"
    - "Incoming: ARMOR (damage blocked this round)"
  - Boss telegraph shown at the start of each round
- Player HP bar also visible (separate from boss)

**Done when:** A boss exists on screen with an HP bar and shows a random telegraph each round start.

---

## Milestone 6 — The Full Combat Round (3–4 hrs)

Wire everything together into a complete round loop. This is the fun gate.

**Round sequence (matches GDD):**

1. Boss telegraphs its action
2. Player draws 5 cards (or remainder of deck)
3. Player groups cards and submits, OR plays cards individually
4. All groups + individuals evaluate simultaneously
5. Damage calculated: `tier × base_damage_constant` (tune this number)
6. Boss action resolves: player takes damage or round is blocked
7. Hand discards, round ends
8. Repeat until boss HP = 0 or player HP = 0

**Deliverables:**

- `CombatRound` state machine:
  - States: `BossTelegraph → PlayerInput → Evaluation → Resolution → Cleanup`
  - Each state transition is explicit, no spaghetti event flow
- Damage formula: `tier × 15` as starting baseline (adjust in playtesting)
- Win/loss condition detected and displayed
- Play again button resets the fight

**Done when:** You can play a complete fight from first draw to boss death (or player death) with no manual console intervention.

---

## Milestone 7 — First Playtest Pass (1–2 hrs)

Not a coding milestone. Play the loop. Break it intentionally.

**Questions to answer:**

- Does drawing 5 cards feel like enough decisions?
- Does grouping feel natural or annoying?
- Is the damage curve interesting? (Does the fight last long enough to feel strategic but short enough to not drag?)
- Do you ever feel stuck with a bad hand and no real options?
- Does the telegraph actually change how you play?

**Deliverables:**

- A short written note (even bullet points) answering the above
- At least 2 tuning changes based on what you felt — damage numbers, HP totals, hand size, anything

**Done when:** You've played 10+ full fights and have opinions about what feels wrong.

---

## Milestone 8 — Joker Logic (2–3 hrs)

Now that the core loop is validated, add the Joker wildcard system.

**Deliverables:**

- `Red Joker` — acts as any card needed to complete the highest possible combo in its group
- `Black Joker` — acts as any card of the player's choice (manual selection prompt)
- `ComboEvaluator` updated to handle Joker substitution
- Visual indicator on Joker cards showing their current resolved identity
- Joker probability: ~2 Jokers in 54-card deck (GDD baseline)

**Done when:** A Red Joker correctly completes a Straight or Flush, and a Black Joker prompts manual suit/rank selection.

---

## Phase 0 Complete — Exit Criteria

Phase 0 is finished when all of the following are true:

- [ ] A full combat fight plays start to finish without intervention
- [ ] Combo detection is correct for all 10 combo types
- [ ] Grouping mode works as designed
- [ ] Joker wildcards resolve correctly
- [ ] You have written playtest notes with at least 2 tuning changes applied
- [ ] The fight feels like it has **decisions** — moments where your grouping choice matters

---

## What Phase 0 Does NOT Include

Explicitly deferred. Do not build these now:

- Gamepad input (keyboard stand-ins only)
- Real card art or visual polish
- Deck persistence or deckbuilding
- Relic system
- Ante/wager system
- Movement or platforming
- Any world content (biomes, NPCs, narrative)
- Card-specific effects from the 52-card identity map
- Sound or music

---

## Carry-Forward Inventory

Every system built in Phase 0 is production code. Here is what survives into the full project:

| System                      | Phase 0 form             | Later upgrade                  |
| --------------------------- | ------------------------ | ------------------------------ |
| `Card` / `DeckState`        | Complete                 | Add variant/upgrade tracking   |
| `ComboEvaluator`            | Complete for base combos | Add Relic modifiers            |
| `CombatRound` state machine | Functional               | Add full card effects, boss AI |
| `DummyBoss`                 | Placeholder              | Replace with real boss actors  |
| `HandDisplay`               | Placeholder visuals      | Replace with card art          |
| `GroupState`                | Complete                 | Add gamepad input layer        |

---

_Wonderland — Phase 0 Plan v1.0_ _Next phase: Phase 1 — Movement Prototype_
