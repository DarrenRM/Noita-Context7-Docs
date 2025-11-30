---
title: Freezing Gaze Projectile Spawner
category: scripts/
---

# Freezing Gaze Projectile Spawner

This script defines the behavior for the "Freezing Gaze" projectile, which spawns multiple smaller beam projectiles in an arc.

## Core Functionality

The primary purpose of this script is to:
1.  Determine the spawn location and orientation based on the parent entity.
2.  Calculate the angles for spawning multiple sub-projectiles in a defined arc.
3.  Spawn these sub-projectiles using `shoot_projectile_from_projectile`.
4.  Destroy the parent "Freezing Gaze" entity after spawning.

## Key Attributes & Elements

*   **`entity_id`**: The unique identifier for the "Freezing Gaze" entity being processed.
*   **`x`, `y`**: The world coordinates of the "Freezing Gaze" entity.
*   **`angle`**: The current rotation of the "Freezing Gaze" entity. This is used to orient the spawned projectiles.
*   **`count`**: The number of sub-projectiles to spawn (set to 12).
*   **`arc`**: The total angular spread of the spawned projectiles (set to `pi * 0.6`, approximately 108 degrees).
*   **`increment`**: The angular difference between each spawned projectile.
*   **`current`**: The starting angle for the arc, adjusted to center it around the parent entity's orientation.
*   **`speed`**: The velocity magnitude for each spawned projectile (set to 220).
*   **`shoot_projectile_from_projectile`**: The core function used to create and launch the sub-projectiles.
    *   **`entity_id`**: The ID of the parent projectile from which the new one is spawned.
    *   **`"data/entities/projectiles/deck/freezing_gaze_beam.xml"`**: The XML definition for the projectile to be spawned (the actual "beam").
    *   **`x`, `y`**: The spawn coordinates.
    *   **`vx`, `vy`**: The velocity components of the spawned projectile.
*   **`EntityKill( entity_id )`**: This function is called to remove the "Freezing Gaze" entity itself after it has served its purpose of spawning the beams.

## Spawning Logic

The script iterates `count` times, calculating the `vx` and `vy` for each sub-projectile using trigonometry (`math.cos` and `math.sin`) based on the `current` angle and the defined `speed`. This creates a fan-like spread of projectiles.

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id    = GetUpdatedEntityID()
local x, y, angle = EntityGetTransform( entity_id )

-- Adjust angle to be relative to the projectile's orientation
angle = 0 - angle

local count = 12
local pi = 3.14159
local arc = pi * 0.6 -- Total arc spread (approx 108 degrees)
local increment = arc / count -- Angular step between projectiles
local current = angle - ( arc * 0.5 ) -- Starting angle, centered
local speed = 220

for i=1,count do
	local vx = math.cos( current ) * speed
	local vy = 0-math.sin( current ) * speed
	
	-- Spawn the actual beam projectile
	shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/freezing_gaze_beam.xml", x, y, vx, vy )
	
	current = current + increment -- Move to the next angle
end

-- Remove the parent "Freezing Gaze" entity
EntityKill( entity_id )
```