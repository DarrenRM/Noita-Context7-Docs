---
title: Weaken End Status Effect
category: scripts/status_effects
---

---

# Weaken End Status Effect

This script handles the "Weaken End" status effect in Noita. When applied, it iterates through all child entities of the player and enables any components tagged with "effect_protection". This is likely intended to prevent certain negative status effects from being applied or to reinforce existing protections.

## Key Functionality

*   **Entity Identification:** Retrieves the current entity ID and the root player entity ID.
*   **Child Entity Iteration:** Loops through all child entities of the player.
*   **Tag-Based Component Enabling:** Specifically targets and enables components with the "effect_protection" tag.

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local player_id = EntityGetRootEntity( entity_id )
local x, y = EntityGetTransform( entity_id )

if ( player_id ~= NULL_ENTITY ) and ( entity_id ~= player_id ) then
	local c = EntityGetAllChildren( player_id )
	
	if ( c ~= nil ) then
		for i,v in ipairs( c ) do
			if EntityHasTag( v, "effect_protection" ) then
				EntitySetComponentsWithTagEnabled( v, "effect_protection", true )
			end
		end
	end
end