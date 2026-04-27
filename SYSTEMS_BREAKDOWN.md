# Systems Breakdown

## Implementation Systems

### Enemy AI
The enemy AI operates on a state machine that handles different behaviors depending on the player's actions. It includes:
- **Patrolling**: Enemies patrol a defined route until they detect the player.
- **Chasing**: Upon detecting the player, enemies transition to a chasing state, closing the distance and attacking if within range.
- **Fleeing**: If health drops below a threshold, enemies may flee to regain health.

### Gamepad Controls
The gamepad controls are mapped as follows:
- **Left Stick**: Move character
- **Right Stick**: Aim
- **A Button**: Jump
- **B Button**: Use item
- **Triggers**: Fire weapon

### Health System
The health system tracks the player's and enemies' health:
- **Health Points (HP)**: Both player and enemies have a set number of health points.
- **Damage Calculation**: Damage is calculated based on weapon type and enemy armor values.
- **Health Regeneration**: Players can regain health through items or specific game events.

### Core Gameplay Systems
- **Inventory System**: Players can collect, store, and use items throughout the game.
- **Quest System**: A quest log tracks player progress through missions and objectives.
- **Save/Load Mechanism**: Players can save game progress at checkpoints and load their last saved game.