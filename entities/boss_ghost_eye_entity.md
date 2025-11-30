---
title: Boss Ghost Eye Entity
category: entities
---

---

# Boss Ghost Eye Entity

This document describes the `eye.lua` entity, which appears to be a component of a boss ghost enemy in Noita. Its primary function is to track and orient itself towards the player.

## Key Attributes and Behavior

*   **Player Tracking:** The entity actively seeks out the nearest player unit.
*   **Orientation:** It calculates the direction towards the player and adjusts its own transform accordingly.
*   **Offset Movement:** The eye entity is positioned slightly offset from its root entity, moving in the direction of the player.

## Lua Script Breakdown

```lua
dofile_once( "data/scripts/lib/utilities.lua" ) -- Loads utility functions.

local entity_id = GetUpdatedEntityID() -- Gets the unique ID of the current entity.
local root_id = EntityGetRootEntity( entity_id ) -- Retrieves the ID of the parent/root entity.
local x,y = EntityGetTransform( root_id ) -- Gets the current position of the root entity.

local angle = 0 -- Initializes an angle variable.
local players = EntityGetWithTag( "player_unit" ) -- Finds all entities tagged as "player_unit".

if ( #players > 0 ) then -- Checks if any players exist in the game.
	local p = players[1] -- Selects the first player found.
	
	local px,py = EntityGetTransform( p ) -- Gets the player's position.
	
	-- Calculates the direction from the eye's root entity to the player.
	angle = get_direction( x, y, px, py ) 
end

-- Inverts the calculated angle to make the eye face away from the player's direction.
angle = math.pi + angle 

-- Updates the eye's transform, positioning it slightly offset from the root entity
-- in the calculated direction.
EntitySetTransform( entity_id, x + math.cos( angle ) * 3, y - math.sin( angle ) * 3 ) 
```

## Potential Modding Applications

*   **Custom Boss Behavior:** Modify the `get_direction` logic or the offset calculation to create unique eye movements or attack patterns for custom boss entities.
*   **Visual Effects:** Integrate this entity as a visual component for other entities that need to track or react to player presence.
*   **AI Enhancements:** Use the player tracking mechanism as a base for more complex AI behaviors in other enemies.