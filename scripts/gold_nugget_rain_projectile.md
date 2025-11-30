---
title: Gold Nugget Rain Projectile
category: scripts
---

# Gold Nugget Rain Projectile

This script defines the behavior for a projectile that spawns gold nuggets. It's designed to create a shower of gold, with the quantity and type of nuggets influenced by the projectile's vertical position.

## Key Attributes

### Spawn Logic

*   **`count`**: Determines the number of gold nuggets to spawn. This is calculated based on the projectile's `pos_y`, with higher positions resulting in more nuggets. The maximum number of nuggets is capped.
*   **`types`**: A table containing the different types of gold nuggets that can be spawned. These likely correspond to different values or sizes of gold.
    *   `"goldnugget"`
    *   `"goldnugget_10"`
    *   `"goldnugget_50"`
    *   `"goldnugget_200"`
*   **`rnd`**: A random value used to select which type of gold nugget to spawn. This value is influenced by the projectile's vertical position; at very high `pos_y`, the chance of spawning rarer/larger nuggets increases.

### Spawn Placement

*   **`raycasts`**: Defines the number of raycasts used to find a suitable, non-wall location for spawning.
*   **`dir`**: The angular separation between raycasts.
*   **`length`**: The distance each raycast travels.
*   **`off_x`, `off_y`**: Random offsets from the projectile's position to determine the spawn point.
*   **`limit`**: A counter to prevent infinite loops if a suitable spawn location cannot be found after a certain number of attempts.
*   **`wall`**: A boolean flag indicating whether a raycast has hit a surface (wall). The script attempts to avoid spawning on walls.

### Entity Spawning

*   **`EntityLoad( "data/entities/items/pickup/" .. entity .. ".xml", pos_x + off_x, pos_y + off_y )`**: This line loads the actual gold nugget entity at the calculated spawn position.
*   **`EntityLoad( "data/scripts/streaming_integration/entities/empty_circle_small_gold.xml", pos_x + off_x, pos_y + off_y )`**: This line loads an additional entity, likely a visual effect or a small marker, associated with the gold spawn.

### Visual Effects

*   **`GameScreenshake( 5 )`**: Triggers a screen shake effect with an intensity of 5, likely to accompany the gold shower.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Initialize random seed based on game frame and entity position
SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

-- Determine the number of gold nuggets to spawn
local count = Random( 1, math.min( math.floor( math.abs( pos_y ) / 1024, 10 ) ) )
-- Define the types of gold nuggets available
local types = { "goldnugget", "goldnugget_10", "goldnugget_50", "goldnugget_200" }

-- Raycast parameters for finding spawn locations
local raycasts = 4
local dir = ( math.pi * 2.0 ) / raycasts
local length = 4

-- Loop to spawn each gold nugget
for i=1,count do
	-- Determine the type of gold nugget to spawn
	local rnd = ( Random(0,2) * Random(0,1) * Random(0,1) ) + 1
	
	-- Increase chance of rarer nuggets at higher altitudes
	if ( math.abs( pos_y ) > 10000 ) then
		rnd = math.min( rnd + Random(0,1), #types )
	end
	
	local entity = types[rnd]
	
	local limit = 0 -- Spawn attempt limit
	local off_x,off_y = 0,0 -- Offset for spawn position
	local wall = true -- Flag to check for walls
	local failed = false -- Flag to indicate if spawning failed
	
	-- Loop to find a suitable spawn location (not too close to origin and not on a wall)
	while ( math.abs( off_x ) + math.abs( off_y ) < 24 ) or wall do
		off_x = Random( -256, 256 )
		off_y = Random( -256, 256 )
		
		local sx = pos_x + off_x
		local sy = pos_y + off_y
		
		-- Perform raycasts to check for walls
		for j=0,raycasts-1 do
			local ex = sx + math.cos( j * dir ) * length
			local ey = sy - math.sin( j * dir ) * length
			
			wall = RaytraceSurfaces( sx, sy, ex, ey )
			
			if wall then
				break -- Stop raycasting if a wall is hit
			end
		end
		
		limit = limit + 1
		if ( limit > 20 ) then
			print( "Couldn't find a good spot" )
			wall = false -- Exit loop if too many attempts
			failed = true
		end
	end
	
	-- Load entities if a suitable spot was found and an entity type was selected
	if ( entity ~= nil ) and ( failed == false ) then
		EntityLoad( "data/entities/items/pickup/" .. entity .. ".xml", pos_x + off_x, pos_y + off_y )
		EntityLoad( "data/scripts/streaming_integration/entities/empty_circle_small_gold.xml", pos_x + off_x, pos_y + off_y )
	end
end

-- Trigger a screen shake effect
GameScreenshake( 5 )
```