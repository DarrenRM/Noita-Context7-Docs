---
title: Electrocution Blast Projectile
category: scripts/
---

# Electrocution Blast Projectile

This script defines the behavior for a projectile that creates an electrical discharge effect.

## Core Functionality

The primary purpose of this script is to spawn an `electricity.xml` entity at a slightly randomized position relative to the projectile's origin, with a significant velocity in a random direction.

## Key Attributes

*   **`entity_id`**: The unique identifier for the projectile entity.
*   **`pos_x`, `pos_y`**: The current X and Y coordinates of the projectile.
*   **`theta`**: A random angle in radians (between 1 and 360 degrees) used to determine the projectile's direction.
*   **`length`**: A constant value (5000) representing the magnitude of the velocity.
*   **`vel_x`, `vel_y`**: The calculated X and Y components of the projectile's velocity, derived from `theta` and `length`.
*   **`shoot_projectile`**: The core function call that spawns the actual electrical effect.

### `shoot_projectile` Parameters

The `shoot_projectile` function is called with the following arguments:

1.  **`entity_id`**: The ID of the entity that is firing the projectile.
2.  **`"data/entities/misc/electricity.xml"`**: The XML file defining the electrical entity to be spawned.
3.  **`pos_x + Random(-28, 28)`**: The X-coordinate for the spawned electricity, with a random offset.
4.  **`pos_y + Random(-28, 28)`**: The Y-coordinate for the spawned electricity, with a random offset.
5.  **`vel_x`**: The calculated X-velocity for the spawned electricity.
6.  **`vel_y`**: The calculated Y-velocity for the spawned electricity.

## Example Usage (Conceptual)

This script would typically be attached to an entity that, upon activation or collision, triggers this projectile to be fired. For instance, a wand or a special spell might use this script to create an area-of-effect electrical burst.

```lua
-- Example of how this script might be triggered (not part of the provided source)
function MySpellActivate( caster_id )
    local caster_x, caster_y = EntityGetTransform( caster_id )
    -- Assuming a projectile entity with this script is pre-defined
    local projectile_entity = EntityLoad( "data/entities/projectiles/electrocution_blast.xml", caster_x, caster_y )
    -- The script within electrocution_blast.xml will then handle spawning the electricity
end
```