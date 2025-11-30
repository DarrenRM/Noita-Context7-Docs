---
title: Drone Shield Aura
category: scripts
---

# Drone Shield Aura

This script implements a protective aura for drones, granting nearby enemies a temporary shield.

## Functionality

The script identifies enemies within a radius of 160 units around the drone. For each valid enemy (one that doesn't already possess a "protection_all_short" effect), it spawns an `effect_protection_all_short_evil.xml` entity as a child of the enemy, applying the shield effect.

## Key Components

*   **Radius:** `r = 160` - The distance at which the aura affects enemies.
*   **Target Tag:** `"enemy"` - The tag used to identify potential targets for the aura.
*   **Shield Effect:** `effect_protection_all_short_evil.xml` - The entity responsible for applying the protective shield.
*   **Child Entity Management:** The script uses `EntityAddChild` to attach the shield effect to affected enemies.
*   **Validation:** It checks for existing "protection\_all\_short" components to prevent stacking or redundant effects.

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )
local r = 160

local targets = EntityGetInRadiusWithTag( x, y, r, "enemy" )

for i,v in ipairs( targets ) do
	if ( v ~= entity_id ) then
		local c = EntityGetAllChildren( v )
		local valid = true
		
		if ( c ~= nil ) then
			for a,b in ipairs( c ) do
				local comps = EntityGetComponent( b, "GameEffectComponent", "protection_all_short" )
				
				if ( comps ~= nil ) then
					valid = false
					break
				end
			end
		end
		
		if valid then
			local eid = EntityLoad( "data/entities/misc/effect_protection_all_short_evil.xml", x, y )
			EntityAddChild( v, eid )
		end
	end
end
```