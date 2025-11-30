---
title: Spirit Aura Weakness Effect
category: scripts
---

# Spirit Aura Weakness Effect

This script implements a "spirit aura" that applies a weakness effect to nearby entities.

## Core Functionality

The script identifies entities within a radius and applies a `spirit_weakness` effect to them. It avoids applying the effect to itself, mimic potions, or entities that already have the effect.

## Key Attributes and Logic

*   **Radius:** `r = 220` - The radius within which the aura searches for targets.
*   **Targeting:**
    *   Searches for entities with the `"homing_target"` tag.
    *   Searches for entities with the `"player_unit"` tag.
    *   Combines both lists of targets.
*   **Exclusions:**
    *   Does not target the entity running the script (`v ~= entity_id`).
    *   Does not target entities with the `"mimic_potion"` tag.
*   **Effect Application:**
    *   Checks if the target entity or its children already have a `GameEffectComponent` with the tag `"spirit_weakness"`.
    *   If the effect is not already present, it loads and applies the `data/entities/misc/effect_spirit_weakness.xml` entity as a child to the target.
*   **Duplicate Prevention:** Uses a `done` table to ensure the effect is applied only once per root entity.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )
local r = 220 -- Aura radius

local targets = EntityGetInRadiusWithTag( x, y, r, "homing_target" )
local targets2 = EntityGetInRadiusWithTag( x, y, r, "player_unit" )
local done = {} -- To prevent applying effect multiple times to the same root entity

-- Combine targets
for i,v in ipairs(targets2) do
	table.insert(targets, v)
end

for i,v in ipairs( targets ) do
	-- Exclude self and mimic potions
	if ( v ~= entity_id and not EntityHasTag( v, "mimic_potion" ) ) then
		local c = EntityGetAllChildren( v )
		local root_id = EntityGetRootEntity( v )
		local valid = true
		
		-- Check if effect is already applied to this root entity
		if ( done[root_id] == nil ) then
			-- Check if any child already has the spirit_weakness effect
			if ( c ~= nil ) then
				for a,b in ipairs( c ) do
					local comps = EntityGetComponent( b, "GameEffectComponent", "spirit_weakness" )
					
					if ( comps ~= nil ) then
						valid = false
						break
					end
				end
			end
			
			-- Apply the effect if valid
			if valid then
				local eid = EntityLoad( "data/entities/misc/effect_spirit_weakness.xml", x, y )
				EntityAddChild( v, eid )
				
				done[v] = 1 -- Mark as done for this entity
			end
		end
	end
end
```