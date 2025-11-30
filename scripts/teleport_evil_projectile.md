---
title: Teleport Evil Projectile
category: scripts
---

# Teleport Evil Projectile

This script defines the behavior for a projectile that teleports the entity that fired it.

## Key Functionality

*   **Projectile Creation:** Spawns a "tentacle" projectile.
*   **Teleportation:** The entity that fired this projectile will be teleported.
*   **Randomization:** The teleportation destination is randomized.

## Core Attributes

The script primarily uses the `shoot_projectile` function to create the projectile.

### `shoot_projectile` Parameters

| Parameter      | Type   | Description                                                                 |
| :------------- | :----- | :-------------------------------------------------------------------------- |
| `entity_id`    | number | The ID of the entity that is firing the projectile.                         |
| `projectile_xml` | string | The path to the XML file defining the projectile's appearance and behavior. |
| `pos_x`        | number | The X-coordinate from which the projectile is fired.                        |
| `pos_y`        | number | The Y-coordinate from which the projectile is fired.                        |
| `vel_x`        | number | The initial horizontal velocity of the projectile.                          |
| `vel_y`        | number | The initial vertical velocity of the projectile.                            |

## Script Logic

1.  **Initialization:**
    *   Retrieves the `entity_id` and its `pos_x`, `pos_y` coordinates.
    *   Sets a random seed based on game frame and entity position for deterministic randomness.

2.  **Velocity Calculation (Commented Out):**
    *   The commented-out lines `vel_x = math.cos( angle ) * length` and `vel_y = math.sin( angle ) * length` suggest that the projectile was *intended* to have an initial velocity, likely to influence its trajectory or the teleportation effect.
    *   However, the current implementation sets `vel_x = 0` and `vel_y = 0`, meaning the projectile is fired with no initial velocity.

3.  **Projectile Firing:**
    *   Calls `shoot_projectile` to create the `tentacle.xml` projectile at the entity's current position with zero initial velocity.

## Associated Files

*   `data/entities/projectiles/tentacle.xml`: Defines the visual and behavioral aspects of the spawned projectile.