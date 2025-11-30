---
title: Vault Lab Puzzle Checker
category: scripts
---

# Vault Lab Puzzle Checker

This script defines the logic for a puzzle within the Vault Lab, specifically handling the success condition. When triggered, it spawns rewards and cleans up puzzle elements.

## Key Functions

### `material_area_checker_success(pos_x, pos_y)`

This function is called when the puzzle's success condition is met.

#### Parameters

*   `pos_x` (number): The X-coordinate of the trigger.
*   `pos_y` (number): The Y-coordinate of the trigger.

#### Behavior

1.  **Get Entity ID and Transform**: Retrieves the ID and current transform of the entity executing this script.
2.  **Determine Spawn Location**: Calculates a spawn point for rewards relative to the entity's position (`spawn_x = x + 70`, `spawn_y = y + 10`).
3.  **Spawn Reward Particle**: Spawns a `magical_symbol.xml` particle effect at the calculated spawn location.
4.  **Play Success Sound**: Plays a specific sound effect (`player_projectiles/crumbling_earth/create`) at the spawn location.
5.  **Randomly Spawn Wand**:
    *   With a 70% probability (if `ProceduralRandomf(x,y) > 0.3`), spawns `wand_arpaluu.xml`.
    *   Otherwise, spawns `wand_varpuluuta.xml`.
6.  **Cleanup Puzzle Elements**: Iterates through all entities within a 30-unit radius that have the tag `"vault_lab_puzzle"` and destroys them.

## Key Attributes/Elements

*   **Reward Spawning**: The script is responsible for spawning visual effects, sound, and a random wand upon puzzle completion.
*   **Randomization**: Introduces a chance-based element for the type of wand awarded.
*   **Puzzle Cleanup**: Ensures that the puzzle's interactive elements are removed after successful completion.
*   **Tag-Based Targeting**: Uses entity tags (`"vault_lab_puzzle"`) for efficient identification and cleanup of puzzle components.
*   **Coordinate System**: Relies on relative positioning for reward spawning and cleanup.