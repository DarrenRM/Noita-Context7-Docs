---
title: Greed Die Status Effect
category: scripts
---

# Greed Die Status Effect

This script defines the behavior of the "Greed Die" item in Noita, specifically its status effect that triggers projectile attacks and item spawns based on a random roll.

## Core Functionality

The script primarily manages a "rolling" status effect. When this status reaches a certain threshold, the Greed Die performs one of several randomized actions, including firing projectiles or spawning special items.

### `bullet_circle` Function

This helper function is responsible for spawning projectiles in a circular pattern around the die.

*   **`which`**: The name of the projectile XML file to spawn (e.g., "buckshot", "meteor_green").
*   **`count`**: The number of projectiles to spawn in the circle. Defaults to 4.
*   **`speed`**: The velocity of the spawned projectiles. Defaults to 200.
*   **`animal_`**: If true, adds a `no_gold_drop` tag to the projectile.
*   **`gold_`**: If true, spawns gold nugget pickups instead of projectiles.

## Status Effect Logic

The script tracks a `status` variable, which increments each frame the die is active.

### Triggering Actions

When `status` reaches 20 or more:

1.  **Reset Status**: `status` is reset to 0.
2.  **Random Roll**: A random number between 1 and 6 (`result`) is generated.
3.  **Special Roll**: A random number between 1 and 100 (`special`) is generated to determine if a "good" or "bad" outcome occurs.

### Outcome Determination

*   **Standard Roll (`special < 100`)**:
    *   A message like `$item_die_X` is printed to the player (where X is the `result`).
    *   The die's animation changes to `rolled_X`.
    *   Specific projectiles are fired based on the `result`:
        *   **1**: Fires 4 "black\_hole\_big" projectiles.
        *   **2**: Fires 12 "meteor\_green" projectiles.
        *   **3**: Fires 16 "orb\_laseremitter" projectiles.
        *   **4**: Fires 16 "goldnugget\_10" pickups.
        *   **5**: Fires 12 "goldnugget\_50" pickups.
        *   **6**: Fires 8 "goldnugget\_200" projectiles.

*   **Special Roll (`special >= 100`)**:
    *   A message like `$item_greed_die_bad` or `$item_greed_die_good` is printed.
    *   The die's animation changes to `rolled_bad` or `rolled_good`.
    *   **Bad Outcome (`result <= 3`)**:
        *   Fires 16 "disc\_bullet\_bigger" projectiles.
        *   The Greed Die entity is destroyed (`EntityKill`).
    *   **Good Outcome (`result > 3`)**:
        *   Spawns two "chest\_random\_super" items.
        *   The Greed Die entity is destroyed (`EntityKill`).

### Animation Update

The `SpriteComponent` of the Greed Die is updated with the appropriate animation based on the roll outcome.

### Status Persistence

The `status` value is updated in a `VariableStorageComponent` to ensure it persists across frames.