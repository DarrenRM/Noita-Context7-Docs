---
title: Lightning Explosion Projectile Spawner
category: scripts
---

# Lightning Explosion Projectile Spawner

This script defines the behavior for spawning multiple lightning projectiles in a radial pattern, simulating an explosion effect. It's designed to be attached to an entity that triggers this projectile barrage.

## Key Attributes

*   **`how_many`**: Determines the number of projectiles to spawn.
*   **`angle_inc`**: Calculates the angular separation between spawned projectiles, incorporating procedural randomness for variation.
*   **`length`**: Sets the initial velocity magnitude for the spawned projectiles.
*   **`theta`**: The current angle used to calculate the velocity vector for each projectile.

## Functionality

The script first checks if a certain cooldown period (10 frames) has passed since the last execution to prevent excessive spawning. If the cooldown is met, it proceeds to:

1.  **Calculate `angle_inc`**: This value is crucial for distributing the projectiles evenly in a circle. It takes the total angle of a circle (`2 * pi`) divided by the number of projectiles (`how_many`) and adds a random offset.
2.  **Loop and Spawn**: It iterates `how_many` times. In each iteration:
    *   It calculates the `vel_x` and `vel_y` components of the projectile's velocity using trigonometry (`math.cos` and `math.sin`) based on the current `theta` and the `length`.
    *   It increments `theta` by `angle_inc` for the next projectile.
    *   It calls `shoot_projectile` to create a new projectile.

## `shoot_projectile` Parameters

The `shoot_projectile` function is called with the following arguments:

*   **`entity_id`**: The ID of the entity that is spawning the projectiles.
*   **`"data/entities/projectiles/lightning_thunderburst.xml"`**: The XML file defining the projectile's properties.
*   **`pos_x`, `pos_y`**: The spawn position of the projectiles, taken from the spawner entity's transform.
*   **`vel_x`, `vel_y`**: The calculated velocity components for the projectile.

## Example Usage

This script would typically be attached to an entity that, upon activation (e.g., by being hit or triggered), executes this Lua code. The result is a burst of lightning projectiles radiating outwards from the entity's position.

```lua
-- Example of how this script might be triggered (conceptual)
-- This is NOT part of the provided script, but illustrates its context.

-- Assume 'my_lightning_spawner_entity' is an entity with this script attached.
-- When 'my_lightning_spawner_entity' is activated:
-- execute_script("data/scripts/projectiles/lightning_explosion_thundermage.lua", my_lightning_spawner_entity)
```