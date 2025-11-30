---
title: Line Arc Projectile Velocity Modifier
category: scripts
---

# Line Arc Projectile Velocity Modifier

This script modifies the velocity of a projectile to align it with cardinal or intercardinal directions (multiples of 45 degrees). It's designed for projectiles that should travel in a straight, quantized path.

## Key Functionality

The script targets the `VelocityComponent` of an entity and adjusts its `mVelocity` vector.

### Velocity Adjustment Logic

1.  **Get Current Velocity:** Retrieves the current `vel_x` and `vel_y` from the `VelocityComponent`.
2.  **Calculate Angle:** Determines the current angle of the velocity vector relative to the positive X-axis.
3.  **Quantize Angle:** Rounds the angle to the nearest 45-degree increment. This ensures the projectile will move along one of the eight primary directions (N, NE, E, SE, S, SW, W, NW).
4.  **Reapply Velocity:** Calculates new `vel_x` and `vel_y` components based on the quantized angle and the original velocity magnitude, ensuring the projectile moves in a straight, quantized direction.

## Relevant Components

*   **`VelocityComponent`**: This is the primary component targeted by the script.
    *   **`mVelocity`**: A `Vector2` value representing the projectile's current velocity. The script reads this value and writes a modified version back.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity that has a `VelocityComponent`. When the projectile is spawned or updated, this script runs, forcing its movement into one of the eight cardinal or intercardinal directions.

```lua
-- Example of how this script might be applied to an entity
-- (This is illustrative and not part of the provided script)

-- Assuming 'my_projectile_entity' is the ID of the projectile
-- and it has a VelocityComponent with initial velocity

-- Add the script to the entity's components
EntityAddComponent( my_projectile_entity, "LuaComponent", {
    script = "data/scripts/projectiles/line_arc.lua",
    execute_order = 1000 -- Or an appropriate order
} )

-- Ensure the entity has a VelocityComponent
EntityAddComponent( my_projectile_entity, "VelocityComponent", {
    mVelocity = { x = 100, y = 50 } -- Example initial velocity
} )
```