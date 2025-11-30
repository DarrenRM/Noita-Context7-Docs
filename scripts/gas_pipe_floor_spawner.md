---
title: Gas Pipe Floor Spawner
category: scripts
---

# Gas Pipe Floor Spawner

This script is responsible for spawning a `gas_pipe_floor.xml` entity when certain conditions are met. It primarily functions by detecting the presence of a suitable floor below the spawner's position.

## Core Functionality

The script performs the following key actions:

1.  **Initialization**: Retrieves the spawner's entity ID and its world coordinates.
2.  **Vertical Search**: Initiates a raycast downwards from the spawner's position to find the nearest platform or floor.
3.  **Floor Detection**: Iterates through a horizontal range around the spawner to find the lowest point of a detected floor.
4.  **Conditional Spawning**: If a floor is successfully detected within the search parameters, it spawns the `gas_pipe_floor.xml` entity at the found floor location.
5.  **Cleanup**: The spawner entity itself is then destroyed.

## Key Attributes and Logic

*   `search_dist_y`: Defines the maximum vertical distance (in pixels) the script will search downwards for a floor.
*   `scatter_x`: Determines the horizontal spread (in pixels) for the raycasts. The script checks for floors within `pos_x - scatter_x` to `pos_x + scatter_x`.
*   `RaytracePlatforms(x, pos_y, x, pos_y + search_dist_y)`: This is the core raycasting function. It checks for a platform along a vertical line.
*   `floor_y > max`: This condition ensures that the script prioritizes the *lowest* detected floor within the search area.
*   `EntityLoad("data/entities/buildings/biome_modifiers/gas_pipe_floor.xml", floor_x, floor_y)`: This function loads and places the `gas_pipe_floor.xml` entity at the calculated `floor_x` and `floor_y` coordinates.
*   `EntityKill(entity_id)`: Removes the spawner entity from the game world after its task is complete.

## Usage Notes

This script is designed to be attached to an entity that acts as a trigger for spawning gas pipe floors. The `gas_pipe_floor.xml` entity itself is likely responsible for the visual and functional aspects of the gas pipe.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
local search_dist_y = 50 -- Vertical search distance
local scatter_x = 8    -- Horizontal scatter for raycasts

-- Check if a world exists at the target search area to avoid unnecessary processing
if not DoesWorldExistAt( pos_x, pos_y + search_dist_y, pos_x, pos_y ) then return end

local floor_found = false
local floor_x = 0
local floor_y = 0
local max = -99999999 -- Initialize with a very small number to find the lowest floor

-- Iterate horizontally to find the lowest floor
for x = pos_x - scatter_x, pos_x + scatter_x, scatter_x do
	local ray_hit,ray_x,ray_y = RaytracePlatforms(x, pos_y, x, pos_y + search_dist_y )
	if ray_hit and floor_y > max then -- If a platform is hit and it's lower than the current lowest
		floor_found = true
		floor_x = ray_x
		floor_y = ray_y
		max = ray_y -- Update the lowest floor position
	end
end

-- Spawn the gas pipe floor if one was found
if floor_found then
	EntityLoad("data/entities/buildings/biome_modifiers/gas_pipe_floor.xml", floor_x, floor_y)
end

-- Remove the spawner entity
EntityKill(entity_id)
```