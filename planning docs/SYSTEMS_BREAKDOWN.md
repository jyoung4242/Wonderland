# Systems Breakdown

## Implementation Systems

### Enemy AI

The enemy AI operates on a state machine that handles different behaviors depending on the player's actions. It includes:

- **Patrolling**: Enemies patrol a defined route until they detect the player.
- **Chasing**: Upon detecting the player, enemies transition to a chasing state, closing the distance and attacking if within range.
- **Fleeing**: If health drops below a threshold, enemies may flee to regain health.

- **Implementation Priority:** High
- **Dependencies:** AI System, Combat System
- **Implementation Phases:**
  1. Basic enemy types creation
  2. AI behavior programming
  3. Combat integration
  4. Balancing and diversity of enemies

### Gamepad Controls

The gamepad controls are mapped as follows:

- **Left Stick**: Move character
- **Right Stick**: Aim
- **A Button**: Jump
- **B Button**: Use item
- **Triggers**: Fire weapon

- **Implementation Priority:** High
- **Dependencies:** User Input Framework
- **Implementation Phases:**
  1. Basic controls setup
  2. Input mapping (keyboard, gamepad)
  3. UI control integration
  4. Refinement based on playtesting

### Health System

The health system tracks the player's and enemies' health:

- **Health Points (HP)**: Both player and enemies have a set number of health points.
- **Damage Calculation**: Damage is calculated based on weapon type and enemy armor values.
- **Health Regeneration**: Players can regain health through items or specific game events.

- **Implementation Priority:** High
- **Dependencies:** Combat System
- **Implementation Phases:**
  1. Define health mechanics and status effects
  2. UI health bar implementation
  3. Health feedback system (e.g., damage indicators)
  4. Testing and adjustments

### Movement & Traversal

- **Implementation Priority:** High
- **Dependencies:** Physics Engine, Animation System
- **Implementation Phases:**
  1. Character movement mechanics
  2. Environment interaction (climbing, jumping)
  3. Pathfinding integration
  4. Polishing and optimization

### Combat

- **Implementation Priority:** High
- **Dependencies:** Animation System, AI System
- **Implementation Phases:**
  1. Basic attack and defense mechanics
  2. Enemy AI behavior for combat
  3. Combat feedback (effects, sounds)
  4. Balancing and optimization

### Deck Management

- **Implementation Priority:** Medium
- **Dependencies:** Game State Management
- **Implementation Phases:**
  1. Basic card functionality and types
  2. Deck building mechanics
  3. Integration with UI
  4. Testing and iteration

### Ante

- **Implementation Priority:** Medium
- **Dependencies:** Game State Management
- **Implementation Phases:**
  1. Define ante mechanics
  2. Integrate with gameplay loop
  3. UI and player feedback
  4. Testing and balancing

### Relic

- **Implementation Priority:** Medium
- **Dependencies:** Inventory System
- **Implementation Phases:**
  1. Define relic types and effects
  2. Implement relic acquisition
  3. Integrate with UI
  4. Playtesting for balance

### Progression

- **Implementation Priority:** High
- **Dependencies:** Game State Management
- **Implementation Phases:**
  1. Define progression metrics (experience, levels)
  2. Implement leveling mechanics
  3. Integration with UI
  4. Iteration based on feedback

### Audio & Visual Feedback

- **Implementation Priority:** Medium
- **Dependencies:** Animation System, Combat System
- **Implementation Phases:**
  1. Implement sound effects for actions
  2. Visual feedback (particle effects)
  3. Integration with gameplay events
  4. Playtesting for polish

### World State & NPC

- **Implementation Priority:** High
- **Dependencies:** Game State Management, AI System
- **Implementation Phases:**
  1. Define world state mechanics
  2. Implement NPC behaviors and interactions
  3. Integration with game progression
  4. Iteration based on player feedback

### Core Gameplay Systems

- **Inventory System**: Players can collect, store, and use items throughout the game.
- **Quest System**: A quest log tracks player progress through missions and objectives.
- **Save/Load Mechanism**: Players can save game progress at checkpoints and load their last saved game.

- **Implementation Priority:** Medium (for Save & Persistence)
- **Dependencies:** Game State Management
- **Implementation Phases:**
  1. Define save data structure
  2. Implement saving and loading mechanisms
  3. Integrate into UI
  4. Testing for reliability
