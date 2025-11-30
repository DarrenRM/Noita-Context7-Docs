---
title: Homunculus Teleportation Script
category: scripts
---

---

# Homunculus Teleportation Script

This script enables a homunculus entity to teleport to the player's location if the distance between them exceeds a certain threshold.

## Key Functionality

*   **Player Proximity Check:** The script continuously checks the distance between the homunculus and the nearest player.
*   **Teleportation Trigger:** If the distance is greater than 160 units, the teleportation sequence is initiated.
*   **Visual Effects:** Spawns `teleportation_source.xml` particle effect at the homunculus's current location and `teleportation_target.xml` at the player's location.
*   **Entity Relocation:** The homunculus entity's transform is updated to the player's position.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Loads utility functions.

local entity_id = GetUpdatedEntityID() -- Gets the unique ID of the homunculus entity.
local x, y = EntityGetTransform( entity_id ) -- Gets the current X and Y coordinates of the homunculus.

local players = EntityGetWithTag( "player_unit" ) -- Finds all entities with the "player_unit" tag.

if ( #players > 0 ) then -- Checks if any players were found.
	local p = players[1] -- Selects the first player found.
	local px,py = EntityGetTransform( p ) -- Gets the player's X and Y coordinates.
	
	local d = math.abs( py - y ) + math.abs( px - x ) -- Calculates the Manhattan distance between the homunculus and the player.
	
	if ( d > 160 ) then -- Checks if the distance exceeds 160 units.
		EntityLoad( "data/entities/particles/teleportation_source.xml", x, y ) -- Loads the teleportation source particle effect.
		EntityLoad( "data/entities/particles/teleportation_target.xml", px, py ) -- Loads the teleportation target particle effect.
		EntitySetTransform( entity_id, px, py ) -- Moves the homunculus entity to the player's position.
	end
end
```

## Key Attributes/Elements

*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity running this script.
*   **`EntityGetTransform( entity_id )`**: Returns the X and Y coordinates of an entity.
*   **`EntityGetWithTag( "player_unit" )`**: Finds all entities tagged as "player\_unit".
*   **`math.abs()`**: Calculates the absolute value, used here for Manhattan distance.
*   **`EntityLoad( filepath, x, y )`**: Spawns an entity (like a particle effect) at specified coordinates.
*   **`EntitySetTransform( entity_id, x, y )`**: Updates the position of an entity.
*   **Distance Threshold**: `160` units.
*   **Particle Effects**: `teleportation_source.xml` and `teleportation_target.xml`.