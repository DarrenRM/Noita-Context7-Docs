---
title: Orb Pink Big Super Projectile Behavior
category: scripts
---

# Orb Pink Big Super Projectile Behavior

This script defines the behavior of the "orb_pink_big_super" projectile in Noita. When this projectile is active, it spawns multiple smaller "orb_pink_big_super_shrapnel" projectiles.

## Key Attributes

*   **Shrapnel Spawning:** The primary function of this projectile is to act as a source for smaller projectiles.
*   **Number of Shrapnel:** It spawns a fixed number of shrapnel projectiles.
*   **Shrapnel Projectile Type:** Specifies the XML file for the shrapnel projectiles to be spawned.
*   **Initial Velocity:** Defines the base velocity applied to the shrapnel projectiles.
*   **Angular Distribution:** The shrapnel projectiles are distributed in a circular pattern around the originating projectile.

## Script Logic

The script iterates a set number of times to spawn each shrapnel projectile.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local amount = 12 -- The number of shrapnel projectiles to spawn.
local theta = math.pi * 2 / amount -- The angle increment for each shrapnel.
local vx = 120 -- Initial horizontal velocity for the first shrapnel.
local vy = 0 -- Initial vertical velocity for the first shrapnel.

for i=1, amount do
	-- Calculate the spawn position slightly offset from the parent projectile.
	local x = pos_x + vx * 0.07
	local y = pos_y + vy * 0.07

	-- Shoot the shrapnel projectile.
	local projectile = shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/orb_pink_big_super_shrapnel.xml", x, y, vx, vy )

	-- Rotate the velocity vector for the next shrapnel.
	vx,vy = vec_rotate(vx, vy, theta)
end
```