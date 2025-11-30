---
title: Rocket Octagon Projectile Behavior
category: scripts
---

# Rocket Octagon Projectile Behavior

This script defines the behavior of the "rocket_octagon" projectile in Noita. When the projectile's velocity falls below a certain threshold, it explodes into eight smaller projectiles arranged in an octagon.

## Key Attributes and Behavior

### Projectile Explosion Logic

*   **Speed Threshold:** The projectile's behavior is triggered when its current speed (`speed`) is less than `50`.
*   **Number of Shots:** Upon triggering, `8` smaller projectiles are fired.
*   **Angular Distribution:** The `8` projectiles are distributed evenly in a circle, with an angular increment (`angle_inc`) of `(math.pi * 2) / 8`.
*   **Projectile Type:** The smaller projectiles fired are of the type `data/entities/projectiles/deck/rocket_downwards.xml`.
*   **Velocity Magnitude:** Each of the `8` smaller projectiles is launched with a velocity magnitude of `150`.
*   **Offset:** The smaller projectiles are spawned with a slight positional offset from the parent projectile's position, calculated as `shot_vel_x * 0.05` and `shot_vel_y * 0.05`.
*   **Self-Destruction:** After firing the `8` projectiles, the parent "rocket_octagon" projectile is destroyed using `EntityKill( entity_id )`.

### Initialization

*   **Entity ID and Position:** The script retrieves the current entity's ID and its `x, y` coordinates.
*   **Initial Velocity:** It reads the initial velocity components (`vel_x`, `vel_y`) of the projectile.
*   **Speed Calculation:** The current speed of the projectile is calculated using the Pythagorean theorem: `math.sqrt( vel_y ^ 2 + vel_x ^ 2 )`.

### Core Function

The primary logic is contained within an `if` statement that checks the projectile's speed. If the speed is below the threshold, the loop for spawning the smaller projectiles is executed.

```lua
--[[
This script defines the behavior of the "rocket_octagon" projectile.
When its velocity drops below a certain threshold, it explodes into 8 smaller projectiles.
]]--

dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local vel_x,vel_y = 0,0

-- Get the current velocity of the projectile
edit_component( entity_id, "VelocityComponent", function(comp,vars)
	vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity" )
end)

local speed = math.sqrt( vel_y ^ 2 + vel_x ^ 2 )

-- Check if the projectile's speed is below the threshold
if ( speed < 50 ) then
	local how_many = 8 -- Number of smaller projectiles to spawn
	local angle = 0
	local angle_inc = (math.pi * 2) / how_many -- Angular increment for even distribution

	-- Loop to spawn the smaller projectiles
	for i=1,how_many do
		-- Calculate the velocity components for the new projectile
		local shot_vel_x = math.cos(angle) * 150
		local shot_vel_y = 0 - math.sin(angle) * 150
		
		angle = angle + angle_inc -- Update angle for the next projectile

		-- Shoot the new projectile from the current projectile
		-- The position is slightly offset based on the calculated velocity
		shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/rocket_downwards.xml", pos_x + shot_vel_x * 0.05, pos_y + shot_vel_y * 0.05, shot_vel_x, shot_vel_y, false )
	end
	
	-- Destroy the parent projectile after spawning the smaller ones
	EntityKill( entity_id )
end
```