---
title: Blue Orb Projectile Spawner
category: scripts
---

---

# Blue Orb Projectile Spawner

This script defines the behavior for a projectile that spawns multiple smaller blue orbs.

## Core Functionality

The primary purpose of this script is to create a burst of `orb_blue.xml` projectiles originating from the position of the entity executing this script.

### Key Attributes

*   **`how_many`**: Determines the number of blue orbs to spawn. In this case, it's set to `8`.
*   **`angle_inc`**: Calculates the angular separation between each spawned orb, ensuring they are evenly distributed in a circle.
*   **`length`**: Controls the initial velocity magnitude of the spawned orbs.
*   **`GameEntityPlaySound`**: Triggers a "duplicate" sound effect when the script is executed.
*   **`shoot_projectile_from_projectile`**: The core function that spawns the `orb_blue.xml` projectiles. It takes the spawner's entity ID, the projectile XML to spawn, its position, and its velocity components.

## Spawning Logic

The script iterates `how_many` times, calculating the velocity vector for each orb to ensure they spread out radially from the spawner.

```lua
local how_many = 8
local angle_inc = ( 2 * 3.14159 ) / how_many
local theta = 0
local length = 150

for i=1,how_many do
	local vel_x = math.cos( theta ) * length
	local vel_y = math.sin( theta ) * length
	theta = theta + angle_inc

	GameEntityPlaySound( entity_id, "duplicate" )
	shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/orb_blue.xml", pos_x, pos_y, vel_x, vel_y )
end
```