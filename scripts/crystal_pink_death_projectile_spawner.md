---
title: Crystal Pink Death Projectile Spawner
category: scripts
---

# Crystal Pink Death Projectile Spawner

This script defines the behavior for a projectile that spawns smaller "crystal pink" projectiles upon death.

## Core Functionality

The `death()` function is triggered when the entity associated with this script is destroyed. It then proceeds to spawn a small cluster of projectiles.

### Key Attributes

*   **Projectile Type:** Spawns projectiles defined by `data/entities/projectiles/rocket_crystal_pink.xml`.
*   **Spawn Count:** Spawns 5 projectiles.
*   **Spread Angle:** The spawned projectiles have a random angular spread, with a maximum deviation of `math.pi * 0.25` (45 degrees) from the initial downward trajectory.
*   **Initial Velocity:** The spawned projectiles have an initial downward velocity of -20 units.
*   **Randomization Seed:** Uses the entity's position (`pos_x`, `pos_y`) to seed the random number generator for projectile spread, ensuring unique patterns.

## Code Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

function death()
	-- Get the entity's current ID and transform (position)
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	-- Define the maximum angle for projectile spread
	local angle_max = math.pi * 0.25

	-- Loop to spawn multiple projectiles
	for i=1,5 do
		local vel_x = 0
		local vel_y = -20 -- Initial downward velocity

		-- Apply random rotation to the velocity vector
		vel_x, vel_y = vec_rotate(vel_x, vel_y, ProceduralRandomf(pos_x, pos_y - i*4.81, -angle_max, angle_max))

		-- Shoot the projectile
		shoot_projectile(
			entity_id, -- The entity that is shooting
			"data/entities/projectiles/rocket_crystal_pink.xml", -- The XML file defining the projectile
			pos_x + vel_x * 0.2, -- X position offset
			pos_y + vel_y * 0.2, -- Y position offset
			vel_x, -- Final X velocity
			vel_y, -- Final Y velocity
			false -- Whether the projectile should be affected by gravity (false means no gravity)
		)
	end
end
```