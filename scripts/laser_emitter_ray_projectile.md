---
title: Laser Emitter Ray Projectile
category: scripts
---

# Laser Emitter Ray Projectile

This script defines the behavior for a projectile that acts as a laser emitter, firing a weaker orb projectile.

## Core Functionality

The primary purpose of this script is to:
*   Determine a random firing angle.
*   Calculate the velocity vector based on the angle and a fixed length.
*   Instantiate a weaker orb laser emitter projectile at the current entity's position with the calculated velocity.

## Key Attributes

*   **`entity_id`**: The unique identifier of the current entity.
*   **`pos_x`, `pos_y`**: The current position of the entity.
*   **`angle`**: A randomly generated angle in radians (0 to 359 degrees) for projectile direction.
*   **`length`**: A fixed value (40) determining the magnitude of the projectile's velocity.
*   **`vel_x`, `vel_y`**: The calculated X and Y components of the projectile's velocity.
*   **`eid`**: The entity ID of the newly spawned projectile.

## Script Logic

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Sets a random seed based on game frame, component ID, and position for varied outcomes.
SetRandomSeed( GameGetFrameNum() + GetUpdatedComponentID(), pos_x + pos_y + entity_id )

-- Generates a random angle between 0 and 359 degrees, then converts it to radians.
local angle = math.rad(Random(0,359))
local length = 40 -- Defines the magnitude of the velocity.

-- Calculates the X and Y components of the velocity vector.
local vel_x = math.cos( angle ) * length
local vel_y = 0 - math.sin( angle ) * length

-- Shoots a projectile from the current entity.
-- The projectile spawned is 'orb_laseremitter_weak.xml'.
local eid = shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/orb_laseremitter_weak.xml", pos_x, pos_y, vel_x, vel_y )
```