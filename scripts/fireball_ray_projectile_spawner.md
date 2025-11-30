---
title: Fireball Ray Projectile Spawner
category: scripts
---

---

# Fireball Ray Projectile Spawner

This script is responsible for spawning a `fireball_ray.xml` projectile. It determines the projectile's initial velocity based on a random angle.

## Key Attributes

*   **Entity ID Retrieval**: Gets the root entity ID for the spawner.
*   **Position Retrieval**: Obtains the `x` and `y` coordinates of the spawner.
*   **Random Seed**: Initializes a random seed based on game frame and entity information for varied projectile behavior.
*   **Angle Generation**: Calculates a random angle between 0 and 359 degrees.
*   **Velocity Calculation**: Determines the `vel_x` and `vel_y` components of the projectile's velocity based on the random angle and a fixed `length` of 3000.
*   **Projectile Spawning**: Calls the `shoot_projectile` function to create the `fireball_ray.xml` projectile at the spawner's position with the calculated velocity.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
entity_id = EntityGetRootEntity( entity_id )

local pos_x, pos_y = EntityGetTransform( entity_id )

SetRandomSeed( GameGetFrameNum() + GetUpdatedComponentID(), pos_x + pos_y + entity_id )

local angle = math.rad(Random(0,359))
local length = 3000

local vel_x = math.cos( angle ) * length
local vel_y = 0 - math.sin( angle ) * length

shoot_projectile( entity_id, "data/entities/projectiles/deck/fireball_ray.xml", pos_x, pos_y, vel_x, vel_y )
```