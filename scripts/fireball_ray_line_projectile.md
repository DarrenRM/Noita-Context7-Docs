---
title: Fireball Ray Line Projectile
category: scripts
---

---

# Fireball Ray Line Projectile

This script defines the behavior for a "fireball ray line" projectile in Noita. When this projectile is spawned, it shoots two smaller "fireball_ray_small" projectiles perpendicular to its own velocity vector.

## Key Functionality

*   **Perpendicular Projectile Spawning:** The primary function of this script is to spawn two additional projectiles at a 90-degree angle to the direction the "fireball_ray_line" is moving.
*   **Velocity Inheritance:** The script reads the velocity of the parent projectile to determine the direction for spawning the new projectiles.
*   **Fixed Length:** The spawned projectiles are given a fixed velocity magnitude (`length = 2000`), regardless of the parent projectile's speed.

## Core Logic

The script performs the following steps:

1.  **Get Entity ID and Position:** Retrieves the unique ID and current position (`pos_x`, `pos_y`) of the projectile entity.
2.  **Read Velocity:** Extracts the current velocity vector (`vel_x`, `vel_y`) of the projectile.
3.  **Calculate Angle:** Determines the angle of the projectile's velocity.
4.  **Calculate Perpendicular Angles:** Computes two angles that are 90 degrees (pi/2 radians) above and below the projectile's current angle.
5.  **Spawn First Projectile:**
    *   Calculates the velocity vector for the first perpendicular projectile using `math.cos` and `math.sin` with the `angle_up`.
    *   Spawns a `fireball_ray_small.xml` projectile at the current position with the calculated velocity.
6.  **Spawn Second Projectile:**
    *   Calculates the velocity vector for the second perpendicular projectile using `math.cos` and `math.sin` with the `angle_down`.
    *   Spawns another `fireball_ray_small.xml` projectile at the current position with this new velocity.

## Key Attributes/Elements

*   **`entity_id`**: The unique identifier for the projectile entity.
*   **`pos_x`, `pos_y`**: The current world coordinates of the projectile.
*   **`vel_x`, `vel_y`**: The current velocity vector of the projectile.
*   **`angle`**: The calculated angle of the projectile's movement.
*   **`length`**: A constant value (2000) defining the magnitude of the velocity for the spawned projectiles.
*   **`angle_up`, `angle_down`**: Angles representing the directions perpendicular to the projectile's movement.
*   **`shoot_projectile_from_projectile()`**: The core function used to spawn new projectiles from an existing one.
*   **`"data/entities/projectiles/deck/fireball_ray_small.xml"`**: The XML file defining the smaller projectiles that are spawned.

## Example Usage (Conceptual)

This script is typically attached to a projectile entity defined in an XML file. When that projectile is created in-game, this Lua script will execute, causing it to split into two smaller projectiles.

```lua
-- Example of how this script might be referenced in a projectile's XML:
-- <Entity name="">
--     <LuaComponent
--         script_path="data/scripts/projectiles/fireball_ray_line.lua"
--         execute_on_spawn="true" />
--     ... other components ...
-- </Entity>
```