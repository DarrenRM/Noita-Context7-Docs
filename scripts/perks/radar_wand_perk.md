---
title: Radar Wand Perk
category: scripts/perks
---

# Radar Wand Perk

This perk provides a visual indicator for nearby wands that are not currently held by the player.

## Functionality

The perk scans a radius around the player for entities tagged with "wand". For each wand found, it calculates its distance and direction relative to the player. Based on the distance, it spawns a visual indicator sprite at a fixed offset from the player.

## Key Attributes

*   **Scan Range:** `range = 500` - The maximum distance from the player to detect wands.
*   **Indicator Offset:** `indicator_distance = 24` - The fixed distance from the player where the indicator sprites are spawned.
*   **Wand Tag:** `"wand"` - The tag used to identify wand entities.
*   **Proximity Indicators:** The perk uses different sprites to indicate proximity:
    *   `data/particles/radar_wand_faint.png`: For wands further than 50% of the scan range.
    *   `data/particles/radar_wand_medium.png`: For wands between 25% and 50% of the scan range.
    *   `data/particles/radar_wand_strong.png`: For wands within 25% of the scan range (and further than 10 units).
*   **Player Exclusion:** The perk specifically ignores wands that are parented to the player (i.e., wands the player is currently holding).

## Lua Script Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
pos_y = pos_y - 4 -- offset to middle of character

local range = 500
local indicator_distance = 24

-- ping nearby wand
for _,id in pairs(EntityGetInRadiusWithTag( pos_x, pos_y, range, "wand")) do
	local wand_x, wand_y = EntityGetTransform(id)
	local parent = EntityGetRootEntity( id );

	if( IsPlayer( parent ) == false ) then

		local dir_x = wand_x - pos_x
		local dir_y = wand_y - pos_y
		local distance = get_magnitude(dir_x, dir_y)

		-- sprite positions around character
		dir_x,dir_y = vec_normalize(dir_x,dir_y)
		local indicator_x = pos_x + dir_x * indicator_distance
		local indicator_y = pos_y + dir_y * indicator_distance

		-- display sprite based on proximity
		if distance > range * 0.5 then
			GameCreateSpriteForXFrames( "data/particles/radar_wand_faint.png", indicator_x, indicator_y )
		elseif distance > range * 0.25 then
			GameCreateSpriteForXFrames( "data/particles/radar_wand_medium.png", indicator_x, indicator_y )
		elseif distance > 10 then
			GameCreateSpriteForXFrames( "data/particles/radar_wand_strong.png", indicator_x, indicator_y )
		end
	end
end
```