---
title: Rain Barrel Entity Spawner
category: scripts
---

# Rain Barrel Entity Spawner

This script is responsible for spawning various physics-based entities around a "rain barrel" entity. It aims to find suitable locations near the barrel, avoiding walls, and then spawns a random entity from a predefined list.

## Key Functionality

*   **Random Entity Spawning:** Selects a random entity from a list of physics props to spawn.
*   **Location Finding:** Iteratively searches for a valid spawn location within a defined radius, ensuring it's not too close to the initial entity and not obstructed by walls.
*   **Wall Detection:** Uses raycasting to check for the presence of walls in potential spawn areas.
*   **Screen Shake:** Triggers a screen shake effect upon successful spawning.

## Core Attributes and Elements

### Entity Types

The script can spawn the following types of entities. These are referenced by a string that is prepended with `data/entities/props/physics_` and appended with `.xml`.

| Type Name        | Description                               |
| :--------------- | :---------------------------------------- |
| `barrel_oil`     | An oil barrel.                            |
| `barrel_burning` | A burning barrel.                         |
| `propane_tank`   | A propane tank.                           |
| `barrel_radioactive` | A radioactive barrel.                     |
| `box_harmless`   | A harmless box.                           |
| `box_explosive`  | An explosive box.                         |
| `pressure_tank`  | A pressure tank.                          |

### Spawning Logic

*   **`count`**: Determines how many entities to attempt to spawn. Currently set to `1`.
*   **`raycasts`**: The number of raycasts used for wall detection. Set to `4`.
*   **`dir`**: The angular separation between raycasts, calculated based on `raycasts`.
*   **`length`**: The length of each raycast. Set to `6`.
*   **Location Search Radius**: The script searches for locations within a radius of `256` units from the initial entity's position.
*   **Minimum Distance**: The spawned entity will be at least `48` units away from the initial entity's position (sum of absolute `off_x` and `off_y`).
*   **Wall Check Loop**: The `while` loop continues until a valid spot is found or a `limit` of `20` attempts is reached.
*   **`failed` Flag**: A boolean flag to indicate if a suitable spawn location could not be found within the attempt limit.

### Visual Feedback

*   **`GameScreenshake( 5 )`**: Triggers a screen shake with an intensity of `5` when an entity is successfully spawned.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Initialize random seed based on game frame and entity position
SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

local count = 1 -- Number of entities to spawn
local types = { "barrel_oil", "barrel_burning", "propane_tank", "barrel_radioactive", "box_harmless", "box_explosive", "pressure_tank" }

local raycasts = 4 -- Number of raycasts for wall detection
local dir = ( math.pi * 2.0 ) / raycasts -- Angular separation of raycasts
local length = 6 -- Length of each raycast

for i=1,count do
	-- Select a random entity type
	local rnd = ( Random( 0,6 ) * Random( 0, 1 ) ) + 1
	local entity = types[rnd]
	
	local limit = 0 -- Attempt limit for finding a spawn spot
	local off_x,off_y = 0,0 -- Offset from the initial entity's position
	local wall = true -- Flag to indicate if a wall is detected
	local failed = false -- Flag to indicate if spawning failed
	
	-- Loop to find a suitable spawn location
	while ( math.abs( off_x ) + math.abs( off_y ) < 48 ) or wall do
		off_x = Random( -256, 256 ) -- Random horizontal offset
		off_y = Random( -256, 256 ) -- Random vertical offset
		
		local sx = pos_x + off_x -- Starting X for raycast
		local sy = pos_y + off_y -- Starting Y for raycast
		
		-- Perform raycasts to check for walls
		for j=0,raycasts-1 do
			local ex = sx + math.cos( j * dir ) * length -- Ending X for raycast
			local ey = sy - math.sin( j * dir ) * length -- Ending Y for raycast
			
			wall = RaytraceSurfaces( sx, sy, ex, ey )
			
			if wall then
				break -- Stop checking if a wall is found
			end
		end
		
		limit = limit + 1
		if ( limit > 20 ) then
			print( "Couldn't find a good spot" )
			wall = false -- Exit loop if limit reached
			failed = true
		end
	end
	
	-- Spawn the entity if a valid spot was found and an entity type was selected
	if ( entity ~= nil ) and ( failed == false ) then
		EntityLoad( "data/entities/props/physics_" .. entity .. ".xml", pos_x + off_x, pos_y + off_y )
	end
end

-- Trigger screen shake
GameScreenshake( 5 )
```