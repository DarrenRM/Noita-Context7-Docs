---
title: Wand Rotation Entity
category: entities
---

---

# Wand Rotation Entity

This entity is designed to rotate towards the nearest player. It's likely used as a component or a standalone entity in the game's environment.

## Core Functionality

The primary purpose of this entity is to dynamically adjust its orientation to face the closest player character.

### Key Attributes & Behavior

*   **`entity_id`**: A unique identifier for the entity.
*   **`x`, `y`**: The current world coordinates of the entity.
*   **`d`**: The current direction (angle) of the entity.
*   **Player Detection**: The entity searches for entities tagged as `"player_unit"`.
*   **Targeting**: If players are found, it calculates the angle (`dir`) from its own position to the first detected player's position.
*   **Orientation Update**: The entity's transform (including its direction) is updated to face the calculated `dir`.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Loads utility functions.

local entity_id    = GetUpdatedEntityID() -- Gets the ID of the current entity.
local x, y, d = EntityGetTransform( GetUpdatedEntityID() ) -- Retrieves the entity's position and direction.

local players = EntityGetWithTag( "player_unit" ) -- Finds all entities with the "player_unit" tag.

if ( players ~= nil ) and ( #players > 0 ) then -- Checks if any players were found.
	local player = players[1] -- Selects the first player found.
	local px,py = EntityGetTransform( player ) -- Gets the player's position.
	local dir = math.atan2( py - y, px - x ) -- Calculates the angle towards the player.

	EntitySetTransform( entity_id, x, y, dir ) -- Updates the entity's transform to face the player.
end
```