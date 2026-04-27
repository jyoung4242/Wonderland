# Wonderland — Phase 0 Implementation Plan
### Card Combat Vertical Slice · ExcaliburJS + TypeScript · Blank Repo

---

## Goal

Prove the card combat loop is fun **in isolation** before any other system is built.

Phase 0 ends when you can sit down, draw a hand, group cards into combos, submit them, watch a placeholder boss telegraph and execute an action, and feel the tension of the ante system — all in a single self-contained scene. No world. No traversal. No narrative. Just the loop.

If the loop feels good here, everything else gets built on solid ground.

---

## What Phase 0 Is NOT

- No platforming or movement system
- No persistent deck (hand is hardcoded for now)
- No real art assets required
- No save/load
- No currency or economy
- No relics
- No actual biome or world map

These are explicitly deferred. Scope discipline here is what makes the prototype useful.

---

## Milestone Breakdown

### M0 — Project Scaffolding
**Done when:** Excalibur boots, shows a blank scene, TypeScript compiles cleanly.

- [ ] Init repo with `npm create excalibur` or manual Vite + Excalibur setup
- [ ] Configure `tsconfig.json` for strict mode
- [ ] Establish folder structure (see below)
- [ ] Create `main.ts` → `Game` instance → `CombatScene` as the only scene
- [ ] Placeholder background color renders

**Folder structure:**
```
src/
  scenes/
    CombatScene.ts
  actors/
    Card.ts
    Hand.ts
    Boss.ts
  systems/
    ComboDetector.ts
    DamageCalculator.ts
  ui/
    HandUI.ts
    BossUI.ts
    TelegraphUI.ts
  data/
    cards.ts        ← card definitions
    combos.ts       ← combo tier table
  main.ts
```

---

### M1 — Card Data Model + Static Hand
**Done when:** 5 hardcoded cards render on screen with suit, rank, and value visible.

#### Card Data Model

```ts
type Suit = 'clubs' | 'diamonds' | 'spades' | 'hearts';
type Rank = 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 'J' | 'Q' | 'K' | 'A';

interface CardDefinition {
  suit: Suit;
  rank: Rank;
  value: number;        // numeric value for combo evaluation (J=11, Q=12, K=13, A=14)
  baseEffect: number;   // damage/effect output when played
}
```

- [ ] Define `cards.ts` with the full 52-card data set (values, base effects)
- [ ] `Card` actor — renders as a colored rectangle with suit symbol + rank text
  - Clubs = dark gray, Diamonds = blue, Spades = black, Hearts = red
- [ ] `Hand` class — holds an array of 5 `Card` instances, positions them in a fan/row
- [ ] Hardcode a starting hand of 5 specific cards for now (e.g. 3♣ 3♦ 7♠ K♥ 2♣)
- [ ] Cards render centered at the bottom of the screen

**No interaction yet.** Just rendering.

---

### M2 — Card Selection + Grouping Mode
**Done when:** Player can select cards and place them into a combo group using keyboard.

This is the most important UX milestone. Get this feeling right.

#### Input Map (keyboard stand-in for gamepad)

| Keyboard Key | Gamepad Equivalent | Action |
|---|---|---|
| `←` / `→` | Left Stick | Navigate between cards |
| `Space` | A Button | Select / deselect card |
| `G` | LT | Enter grouping mode |
| `Enter` | RT | Submit current group as combo |
| `Escape` | B Button | Cancel grouping mode |

#### Grouping Mode Rules (from GDD)
- Player selects 2–5 cards, then presses LT to enter grouping mode
- In grouping mode, selected cards are visually staged as a pending combo
- RT submits the group for combo evaluation
- Unsubmitted cards are played individually at end of round
- Multiple combos can be submitted per round

- [ ] Cards highlight on hover/focus
- [ ] Selected cards lift visually (y-offset) and show a selection indicator
- [ ] `G` key enters grouping mode — selected cards move to a "staging area" above the hand
- [ ] Staged combo group is visually distinct from remaining hand
- [ ] `Enter` submits staged group → triggers combo evaluation (M3)
- [ ] `Escape` returns staged cards to hand, clears selection
- [ ] After submission, remaining hand cards are individually queued for play

---

### M3 — Combo Detection Engine
**Done when:** `ComboDetector` correctly identifies all combo tiers from the GDD for any submitted group of cards.

#### Combo Tier Table (implement in order of complexity)

| Priority | Combo Name | Detection Logic |
|---|---|---|
| 1 | High Card | No match — fallback |
| 2 | Pair | 2 cards, matching rank |
| 3 | Two Pair | 2 + 2 cards, two distinct matching ranks |
| 4 | Three of a Kind | 3 cards, matching rank |
| 5 | Straight | 5 cards, sequential ranks (A-low and A-high both valid) |
| 6 | Flush | 4+ cards, matching suit |
| 7 | Full House | 3-of-a-kind + Pair |
| 8 | Four of a Kind | 4 cards, matching rank |
| 9 | Straight Flush | Straight + all same suit |
| 10 | Royal Flush | 10-J-Q-K-A, same suit |
| 11 | Five of a Kind | 5 cards, same rank (requires Joker) |
| 12 | Joker Flush | All 5 cards same suit including at least one Joker |

```ts
// ComboDetector.ts
interface ComboResult {
  tier: ComboTier;
  name: string;
  cards: CardDefinition[];
  damageMultiplier: number;
}

function detectCombo(cards: CardDefinition[]): ComboResult { ... }
```

- [ ] Implement each tier detection in priority order
- [ ] Highest qualifying tier wins — no stacking
- [ ] Write simple unit tests (or manual console test cases) for each tier before moving on
- [ ] `DamageCalculator.ts` — takes a `ComboResult`, returns final damage value
  - Formula: `sum of card baseEffect values × combo multiplier`

#### Combo Multipliers (placeholder values — balance later)

| Tier | Multiplier |
|---|---|
| High Card | 1.0× |
| Pair | 1.5× |
| Two Pair | 2.0× |
| Three of a Kind | 2.5× |
| Straight | 3.0× |
| Flush | 3.0× |
| Full House | 3.5× |
| Four of a Kind | 4.5× |
| Straight Flush | 6.0× |
| Royal Flush | 8.0× |
| Five of a Kind | 10.0× |
| Joker Flush | 10.0× |

---

### M4 — Placeholder Boss + Telegraph System
**Done when:** A boss actor sits on screen, telegraphs an action each round, and executes it after the player submits their hand.

The telegraph system is the core of what makes combat readable and strategic. Build it right even at placeholder fidelity.

#### Boss Data Model

```ts
interface BossAction {
  name: string;
  damage: number;
  telegraphDuration: number;   // ms the telegraph is shown before execution
  telegraphLabel: string;      // what the player sees: "HEAVY STRIKE", "SHIELD UP", etc.
}

interface BossDefinition {
  name: string;
  maxHP: number;
  actions: BossAction[];
  currentHP: number;
}
```

#### Placeholder Boss — "The Iron Soldier" (Clubs stand-in)

| Action | Damage | Telegraph Label |
|---|---|---|
| Heavy Strike | 15 | ⚠ HEAVY STRIKE |
| Armor Up | 0 (gains 10 armor) | 🛡 ARMOR UP |
| Double Hit | 8+8 | ⚡ DOUBLE HIT |
| Recover | -20 HP (heals self) | ✦ RECOVERING |

- [ ] `Boss` actor — simple rectangle/shape, HP bar above it
- [ ] Boss randomly selects an action at the start of each round
- [ ] `TelegraphUI` — displays the chosen action prominently for 1.5s before round begins
  - Large text, distinct color (red for damage, yellow for buff, green for heal)
  - Should feel like a warning the player must react to
- [ ] After player submits all combos, boss executes its telegraphed action
- [ ] Boss takes damage equal to total player output for the round
- [ ] Player takes damage equal to boss action damage
- [ ] Armor mechanic: if boss used "Armor Up", incoming damage is reduced by armor value, then armor resets

---

### M5 — Combat Round Loop
**Done when:** A full round resolves end-to-end and the next round begins automatically.

#### Round Sequence

```
1. TELEGRAPH PHASE
   → Boss selects and displays action (1.5s display)

2. PLAYER PHASE
   → Player draws 5 cards (from shuffled hardcoded pool for now)
   → Player selects, groups, and submits combos
   → Remaining ungrouped cards play individually as High Card
   → Player confirms end of turn

3. RESOLUTION PHASE
   → All player combos resolve in submission order
   → Damage numbers display on boss
   → Boss action resolves
   → Damage number displays on player

4. END OF ROUND
   → Check win condition (boss HP ≤ 0)
   → Check lose condition (player HP ≤ 0)
   → If neither: begin next round from step 1
```

- [ ] `CombatScene` orchestrates the round state machine
- [ ] Use a simple enum for round phase: `Telegraph | PlayerTurn | Resolution | EndCheck`
- [ ] Damage numbers appear as floating text actors that fade out (Excalibur `Label` + `fade` action)
- [ ] HP bars animate smoothly on damage
- [ ] Round counter displayed in UI corner

---

### M6 — Ante System (Minimal Version)
**Done when:** Before combat begins, the player can wager a card from their hand, and that card is at risk of permanent loss on defeat.

This doesn't need economy or currency yet. Just the core emotional mechanic: **something real is at stake.**

#### Phase 0 Ante Flow

1. Pre-combat screen shows current hand
2. Player selects 0 or 1 card to ante (optional at this stage)
3. Anted card is displayed in a "wagered" slot, visually separated
4. If player wins: anted card returns + a bonus card is added to the pool (hardcoded reward)
5. If player loses: anted card is permanently removed from the pool

- [ ] Pre-combat `AnteScene` — simple card selection UI
- [ ] Anted card stored in `GameState` singleton
- [ ] Win/loss resolution checks `GameState.antedCard` and applies result
- [ ] Visual treatment: anted card shown in a "stake" display during combat so the player never forgets what's at risk

---

### M7 — Win / Loss States + Loop Reset
**Done when:** The fight has a clear ending and the player can restart without refreshing the browser.

- [ ] Win screen: boss defeated, combo stats summary (highest combo achieved, total damage)
- [ ] Loss screen: player HP reached zero, anted card lost (if any)
- [ ] "Fight Again" button resets the scene — reshuffles cards, resets boss HP, runs ante selection again
- [ ] This creates the first repeatable prototype loop

---

## Phase 0 Success Criteria

Before calling Phase 0 complete and moving to Phase 1, each of the following must be true:

- [ ] A full fight can be played start to finish without errors
- [ ] All 12 combo tiers detect correctly
- [ ] The telegraph system makes boss actions feel readable and anticipatable
- [ ] The ante selection creates a moment of genuine hesitation
- [ ] Losing an anted card feels bad in a good way
- [ ] The loop is replayable without browser refresh
- [ ] The card grouping UX feels responsive and unambiguous

If any of these feel wrong — especially the grouping UX or telegraph timing — **stop and fix them before Phase 1.** These are the hardest things to retrofit.

---

## Architecture Notes

### State Management
Use a simple `GameState` singleton rather than Excalibur's scene state. Keep it flat:

```ts
// GameState.ts
export const GameState = {
  cardPool: CardDefinition[],     // the player's full card collection
  currentHand: CardDefinition[],  // 5 cards dealt this round
  antedCard: CardDefinition | null,
  playerHP: number,
  playerMaxHP: number,
  roundNumber: number,
};
```

### Scene Flow (Phase 0 only)
```
main.ts
  └── CombatScene
        ├── AnteScene (pre-fight overlay)
        ├── TelegraphPhase
        ├── PlayerPhase
        ├── ResolutionPhase
        └── EndScene (win/loss overlay)
```

### Excalibur-Specific Notes
- Use `Scene.onInitialize()` for one-time setup, `Scene.onActivate()` for per-fight reset
- Cards as `Actor` instances — use `PointerEvent` for mouse/touch, custom keyboard handler for gamepad sim
- Floating damage numbers: `Label` actor + `Actions.fade()` + `Actions.moveBy()`
- HP bars: `Actor` with width scaled to HP ratio, updated each resolution phase
- Telegraph timer: `ex.Timer` with `repeats: false`

---

## What Phase 1 Will Build On

Once Phase 0 proves the combat loop:

- **Phase 1** — Movement prototype in an isolated playground level (wall jump → dash → grapple)
- **Phase 2** — First integrated loop: a platforming room leads to a boss door, card combat on entry
- **Phase 3** — Clubs biome: safe zone, NPC, Jack of Clubs boss, first real deck persistence

The card combat system built in Phase 0 should require **zero structural changes** to integrate into Phase 2. That's the test of whether the architecture was right.

---

*Wonderland GDD v0.1 · Phase 0 Plan v1.0*
