---
title: HPCrystal Entity Script
category: scripts
---

---

# HPCrystal Entity Script

This script defines the behavior for the HPCrystal entity in Noita, primarily focused on healing nearby enemies when the player is within range.

## Core Functionality: `heal_someone()`

The `heal_someone()` function is the main logic driver for the HPCrystal. It executes periodically and performs the following actions:

### Key Actions:

1.  **Entity Identification:**
    *   Retrieves the `entity_id` of the HPCrystal itself.
    *   Gets the `x, y` coordinates of the HPCrystal.

2.  **Player Proximity Check:**
    *   Searches for entities with the tag `"player_unit"` within a `radius` of 192 units around the HPCrystal.

3.  **LuaComponent Check:**
    *   Locates a `LuaComponent` with the name `"hpcrystal_effect"` attached to the HPCrystal. This component controls the script's execution frequency.

4.  **Enemy Targeting (if player is near):**
    *   If a player is found:
        *   Gets the player's `px, py` coordinates.
        *   Searches for entities tagged `"enemy"` within a radius of 85% of the HPCrystal's radius around the player.

5.  **Randomized Healing Application:**
    *   If enemies are found:
        *   Sets a random seed based on the game frame and HPCrystal's position/ID.
        *   Enters a loop (`tries` up to `maxtries` of 50) to find a suitable enemy to heal.
        *   For each selected enemy:
            *   Retrieves its `DamageModelComponent`.
            *   Checks if the enemy's current `hp` is less than its `max_hp`.
            *   If the enemy is not at full health:
                *   Loads and attaches a `fullheal.xml` entity to the target enemy, effectively healing it.
                *   Resets the `hpcrystal_effect` LuaComponent's `execute_every_n_frame` to 180 (longer delay after healing).
                *   Breaks the targeting loop (`tries = 99`).

6.  **Execution Delay Adjustment:**
    *   If the targeting loop completes without finding a suitable enemy to heal (`tries` is less than `maxtries` but not 99), the `execute_every_n_frame` of the `hpcrystal_effect` LuaComponent is set to 30 (shorter delay, attempting again sooner).

### Key Attributes/Elements:

*   **`radius`**: The detection radius for the player (192 units).
*   **`"player_unit"` tag**: Used to identify the player entity.
*   **`"enemy"` tag**: Used to identify potential targets for healing.
*   **`"hpcrystal_effect"` LuaComponent**: Manages the script's execution interval.
    *   **`execute_every_n_frame`**: Controls how often the `heal_someone` function runs.
*   **`"DamageModelComponent"`**: Component on enemies used to check and modify HP.
*   **`EntityLoad("data/entities/misc/fullheal.xml", x, y)`**: Spawns a healing effect entity.
*   **`maxtries` (50)**: Maximum attempts to find a healable enemy per execution.