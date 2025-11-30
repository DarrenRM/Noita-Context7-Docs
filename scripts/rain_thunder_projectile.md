---
title: Rain Thunder Projectile
category: scripts
---

# Rain Thunder Projectile

This script defines the behavior for a projectile that simulates a "rain thunder" effect. It's designed to be triggered by an entity and spawns additional lightning arcs.

## Key Attributes

*   **`entity_id`**: The unique identifier of the entity that spawned this projectile.
*   **`pos_x`, `pos_y`**: The current X and Y coordinates of the projectile.
*   **`SetRandomSeed`**: Initializes the random number generator based on game frame and entity position for deterministic randomness.
*   **`shoot_projectile`**: The core function used to spawn other projectiles.

## Projectile Spawning Logic

The script uses a simple conditional to determine if additional projectiles should be spawned.

### `if (rnd == 1)`

This condition, currently hardcoded to always be true due to `rnd` being initialized to `1`, dictates the spawning of secondary projectiles.

*   **`offset_x = Random( -32, 32 )`**: A random horizontal offset is generated to vary the position of the spawned lightning.
*   **`shoot_projectile( entity_id, "data/entities/projectiles/deck/lightning_extra_arcs.xml", pos_x + offset_x, pos_y + 13, 0, 4000 )`**: This is the primary action. It spawns a new projectile defined by `lightning_extra_arcs.xml`.
    *   **`entity_id`**: The original entity that triggered this rain thunder.
    *   **`"data/entities/projectiles/deck/lightning_extra_arcs.xml"`**: The XML file defining the appearance and behavior of the spawned lightning arcs.
    *   **`pos_x + offset_x`**: The X-coordinate for the new projectile, with the random horizontal offset applied.
    *   **`pos_y + 13`**: The Y-coordinate for the new projectile, slightly above the current projectile's position.
    *   **`0`**: The initial angle of the spawned projectile.
    *   **`4000`**: The speed of the spawned projectile.