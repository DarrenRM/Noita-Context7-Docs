---
title: Horizontal Wall Projectile
category: scripts
---

# Horizontal Wall Projectile

This script defines the behavior of a projectile that creates horizontal walls. When this projectile is active, it spawns other entities to construct a wall.

## Key Attributes and Behavior

*   **Projectile Creation:** The script uses `shoot_projectile_from_projectile` to spawn other entities.
*   **Wall Construction:** It spawns two `wall_builder` projectiles, one moving horizontally to the right (`vel_x`) and another to the left (`0 - vel_x`). This creates a horizontal wall segment.
*   **Wall Piece:** A `wall_piece` projectile is also spawned, likely to form the visual or physical component of the wall.
*   **Sound Effect:** A sound effect is played upon projectile creation using `GamePlaySound`.
*   **Entity Loading:** A `wall_sound` entity is loaded at the projectile's position, potentially for additional audio feedback or effects related to wall construction.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local vel_x = 500 -- Horizontal velocity for wall builders
local vel_y = 0   -- Vertical velocity (no vertical movement for wall builders)

-- Play a sound effect when the projectile is created
GamePlaySound( "data/audio/Desktop/projectiles.bank", "player_projectiles/bullet_laser/create", pos_x, pos_y )

-- Spawn the visual/physical wall piece
shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/wall_piece.xml", pos_x, pos_y, 0, 0 )

-- Spawn wall builders to construct the horizontal wall
-- One moves to the right
shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/wall_builder.xml", pos_x, pos_y, vel_x, vel_y )
-- One moves to the left
shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/wall_builder.xml", pos_x, pos_y, 0 - vel_x, vel_y )

-- Load an entity for wall construction sound effects
EntityLoad( "data/entities/projectiles/deck/wall_sound.xml", pos_x, pos_y )
```