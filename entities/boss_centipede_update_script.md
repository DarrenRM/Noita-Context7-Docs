---
title: Boss Centipede Update Script
category: entities
---

# Boss Centipede Update Script

This script governs the behavior and combat mechanics of the Boss Centipede entity in Noita. It handles its initialization, attack patterns, and reactions to player actions and game state.

## Core Mechanics

The Boss Centipede's behavior is dynamically adjusted based on the number of orbs the player has collected. This influences its health, resistances, and the types of attacks it uses.

### Initialization (`init_boss`)

-   **One-time Initialization:** Ensures the boss is initialized only once per game session.
-   **Orb Count Integration:** Reads the current run's orb count and adds any New Game Plus counts to determine overall difficulty.
-   **Dynamic HP Scaling:** Boss health is calculated using a formula that exponentially increases with the orb count.
-   **Shield Adjustment:** Spawns a weaker shield for 0 orbs, and a stronger one for more.
-   **Damage Resistance & Weakness:**
    -   Higher orb counts grant increased resistances to various damage types (melee, drill, projectile, fire, ice, electricity, acid, slice, physics, radioactive, poison).
    -   Specific orb counts unlock weaknesses to certain magical liquids and materials.
    -   Above 30 orbs, the boss becomes immune to "touch" spells.
-   **Limb Activation:** Enables components on the boss's child entities (limbs) that were initially disabled.
-   **Aggro State:** Detects if the boss was previously in an "aggro" state (e.g., from a previous encounter or save load).

### States (`states` enum)

This enum synchronizes with C++ logic for the boss's movement and AI states:

| State Name                  | Value | Description                               |
| :-------------------------- | :---- | :---------------------------------------- |
| `MoveAroundNest`            | 0     | Default movement within its arena.        |
| `FollowPlayer`              | 1     | Moves towards the player's current position. |
| `Escape`                    | 2     | (Not explicitly used in this script)      |
| `DontMove`                  | 3     | Boss remains stationary.                  |
| `MoveTo`                    | 4     | Moves to a specific target coordinate.    |
| `MoveDirectlyTowardsPlayer` | 5     | Aggressively moves directly at the player. |

### Global Variables

-   `is_dead`: Tracks if the boss has been defeated.
-   `boss_chase`: Controls the "cell eating" chase behavior when the player is far away.
-   `is_eye_open`: Indicates if the boss's "eye" (mouth/attack indicator) is open.
-   `is_aggro`: Boolean flag for when the boss enters its heightened aggression state.
-   `orbcount`: Stores the calculated orb count for the current run.
-   `shield_enabled`: Tracks the current state of the boss's shield.
-   `did_wait`: Used internally by the coroutine loop to prevent infinite loops.
-   `death_sound_started`: Flag to ensure the death sound plays only once.

## Combat Phases (`next_phase`, `phase_*` functions)

The `next_phase` function orchestrates the boss's attack sequence. It selects from a pool of available attack phases, with the selection influenced by player distance and orb count.

### Key Attack Phases:

| Phase Function Name     | Description