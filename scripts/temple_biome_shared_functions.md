---
title: Temple Biome Shared Functions
category: scripts/
---

# Temple Biome Shared Functions

This document outlines shared Lua functions used within the Noita temple biomes, primarily for managing game state, entity spawning, and biome-specific logic. These functions are crucial for modders looking to interact with or modify temple-related gameplay elements.

## Key Functions

### `temple_pos_to_id( pos_x, pos_y )`

Converts world coordinates into a unique string identifier for a specific temple section. This is useful for tracking states or events within discrete areas of the temple.

*   **Parameters:**
    *   `pos_x` (number): The X-coordinate.
    *   `pos_y` (number): The Y-coordinate.
*   **Returns:**
    *   `string`: A unique ID in the format "W_H", where W and H represent the calculated grid coordinates.

### `temple_set_active_flag( pos_x, pos_y, flag )`

Sets a global flag associated with a specific temple location. This is likely used to mark areas as active, cleared, or in a particular state.

*   **Parameters:**
    *   `pos_x` (number): The X-coordinate of the temple section.
    *   `pos_y` (number): The Y-coordinate of the temple section.
    *   `flag` (any): The value to set for the flag.
*   **Notes:**
    *   It finds the closest entity with the tag "workshop_aabb" to determine the relevant global key.

### `temple_spawn_guardian( pos_x, pos_y )`

Handles the spawning of a guardian entity (likely a Necromancer Shopkeeper) in the temple. It includes logic to prevent spawning if the "peace\_with\_gods" perk is active.

*   **Parameters:**
    *   `pos_x` (number): The X-coordinate for potential spawning.
    *   `pos_y` (number): The Y-coordinate for potential spawning.
*   **Logic:**
    *   Checks the global value of "TEMPLE\_PEACE\_WITH\_GODS". If it's "1", the function returns without spawning.
    *   Attempts to find an entity with the tag "guardian\_spawn\_pos" to determine a precise spawn location.
    *   If found, it uses that entity's transform. Otherwise, it uses the provided `pos_x` and `pos_y`.
    *   Kills the "guardian\_spawn\_pos" entity after use to prevent re-spawning.
    *   Loads the "data/entities/misc/spawn\_necromancer\_shop.xml" entity at the determined spawn coordinates.

### `temple_should_we_spawn_checkers( pos_x, pos_y )`

Determines whether "checkers" (likely referring to some form of environmental hazard or event trigger) should spawn in a given temple location. It checks for pre-existing "leaked" or "collapsed" states.

*   **Parameters:**
    *   `pos_x` (number): The X-coordinate of the temple section.
    *   `pos_y` (number): The Y-coordinate of the temple section.
*   **Returns:**
    *   `boolean`: `true` if checkers should spawn, `false` otherwise.
*   **Conditions for returning `false`:**
    *   `DESIGN_TEMPLE_CHECK_FOR_LEAKS` magic number is "0".
    *   A global flag `TEMPLE_LEAKED_W_H` is set to "1".
    *   A global flag `TEMPLE_COLLAPSED_W_H` is set to "1".

### `temple_random( x, y )`

A utility function that appears to control random events or spawns within the temple, potentially related to leaks or perk availability.

*   **Parameters:**
    *   `x` (number): An X-coordinate (purpose not fully clear from context, might be unused or for future expansion).
    *   `y` (number): A Y-coordinate (purpose not fully clear from context, might be unused or for future expansion).
*   **Returns:**
    *   `string`, `string`: Two string values, typically "1", "1".
*   **Logic:**
    *   If the `DESIGN_TEMPLE_CHECK_FOR_LEAKS` magic number is "0", it immediately returns "1", "1".
    *   The commented-out section suggests it might have previously controlled perk spawning based on a "TEMPLE\_LEAKED" global flag.

---
```lua
function temple_pos_to_id( pos_x, pos_y )
	local h = math.floor( pos_y / 512 )
	local w = math.floor( ( pos_x + (32*512) ) / (64*512) )

	local result = tostring(w) .. "_" .. tostring(h)
	return result
end

function temple_set_active_flag( pos_x, pos_y, flag )
	local workshop_aabb = EntityGetClosestWithTag( pos_x, pos_y, "workshop_aabb")
	if workshop_aabb ~= 0 then
		local x,y = EntityGetTransform( workshop_aabb )
		local key = "TEMPLE_ACTIVE_" .. tostring(math.floor(x)) .. "_" .. tostring(math.floor(y))
		GlobalsSetValue( key, flag )
	end
end

function temple_spawn_guardian( pos_x, pos_y )

	if( GlobalsGetValue( "TEMPLE_PEACE_WITH_GODS" ) == "1" ) then
		-- peace_with_gods perk
		return
	end

	local guard_spawn_id = EntityGetClosestWithTag( pos_x, pos_y, "guardian_spawn_pos" )
	local guard_x = pos_x
	local guard_y = pos_y

	-- if distance is too far
	if( guard_spawn_id ~= 0  ) then
		guard_x, guard_y = EntityGetTransform( guard_spawn_id )
		
		--[[local distance = math.abs( guard_x - spawn_pos_x ) + math.abs( guard_y - spawn_pos_y )
		if( distance < 640 ) then
			guard_x = spawn_pos_x
			guard_y = spawn_pos_y
		end
		]]--

		-- kill the spawn target, so that it doesn't come and haunt us in subsequent spawns
		EntityKill( guard_spawn_id )
	end

	EntityLoad( "data/entities/misc/spawn_necromancer_shop.xml", guard_x, guard_y )
	-- this is now handled by game_music.cpp
	--[[if BiomeMapGetName() == "$biome_holymountain" then
		GameTriggerMusicFadeOutAndDequeueAll( 4.0 )
		GameTriggerMusicEvent( "music/temple/necromancer_shop", true, pos_x, pos_y )
	end]]--
end

-- return bool
function temple_should_we_spawn_checkers( pos_x, pos_y )
	if( MagicNumbersGetValue( "DESIGN_TEMPLE_CHECK_FOR_LEAKS") == "0" ) then
		return false
	end

	local leak_name = "TEMPLE_LEAKED_" .. temple_pos_to_id( pos_x, pos_y )

	if( GlobalsGetValue( leak_name ) == "1" ) then
		return false
	end

	local collapse_name = "TEMPLE_COLLAPSED_" .. temple_pos_to_id( pos_x, pos_y )

	if( GlobalsGetValue( collapse_name ) == "1" ) then
		return false
	end
	return true
end


-- return values "1", "1"
-- return values spawn_shop, spawn_perks
function temple_random( x, y )
	if( MagicNumbersGetValue( "DESIGN_TEMPLE_CHECK_FOR_LEAKS") == "0" ) then
		return "1", "1"
	end

	--if( GlobalsGetValue( "TEMPLE_LEAKED" ) == "1" ) then
	--	return "1", "0"
	--end

	return "1", "1"
end
```