---
title: Rocket Downwards Projectile Behavior
category: scripts
---

# Rocket Downwards Projectile Behavior

This script defines the behavior of a projectile that, when its vertical velocity exceeds a certain threshold, spawns multiple smaller rockets that spread outwards and downwards.

## Key Attributes and Logic

### Projectile Spawning

*   **Trigger Condition:** The script activates when the projectile's `vel_y` (vertical velocity) is greater than `10`.
*   **Number of Rockets Spawned:** `how_many = 5` rockets are spawned.
*   **Spawned Projectile Type:** `data/entities/projectiles/deck/rocket_downwards.xml` is used for the spawned projectiles.

### Spawned Rocket Velocities

The script defines a specific set of initial velocities for the spawned rockets, creating a spread pattern.

| Index | `shot_vel_x` | `shot_vel_y` | Description                               |
| :---- | :----------- | :----------- | :---------------------------------------- |
| 1     | -100         | 100          | Leftward and downward velocity            |
| 2     | -50          | 140          | More downward, less leftward velocity     |
| 3     | 0            | 160          | Purely downward velocity                  |
| 4     | 50           | 140          | More downward, less rightward velocity    |
| 5     | 100          | 100          | Rightward and downward velocity           |

### Spawn Offset

The spawned rockets are positioned slightly offset from the original projectile's position, calculated as `pos_x + shot_vel_x * 0.05` and `pos_y + shot_vel_y * 0.05`. This ensures they don't spawn directly on top of each other.

### Self-Destruction

After spawning the secondary projectiles, the original projectile is destroyed using `EntityKill( entity_id )`.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

local vel_x,vel_y = 0,0

-- Get the current velocity of the projectile
edit_component( entity_id, "VelocityComponent", function(comp,vars)
	vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity" )
end)

-- Check if the vertical velocity is high enough to trigger spawning
if ( vel_y > 10 ) then
	local how_many = 5
	-- Define the velocities for the spawned projectiles
	local velocities = {{-100,100},{-50,140},{0,160},{50,140},{100,100}}

	-- Loop through the defined velocities and spawn projectiles
	for _,values in ipairs(velocities) do
		local shot_vel_x = values[1]
		local shot_vel_y = values[2]

		-- Spawn a new projectile from the original projectile
		shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/rocket_downwards.xml", pos_x + shot_vel_x * 0.05, pos_y + shot_vel_y * 0.05, shot_vel_x, shot_vel_y, false )
	end
	
	-- Destroy the original projectile
	EntityKill( entity_id )
end
```