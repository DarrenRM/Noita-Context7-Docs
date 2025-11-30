---
title: Invisibility Machine Entity
category: entities
---

---

# Invisibility Machine Entity

This entity, when activated, applies a permanent invisibility effect to all nearby enemies that do not already possess the "biome_modifier_effect" tag.

## Key Functionality

*   **Targeting:** Identifies all entities with the "enemy" tag.
*   **Effect Application:** For each identified enemy, it attempts to apply the "INVISIBILITY" game effect.
*   **Duration:** The invisibility effect is set to last indefinitely (`frames = -1`).
*   **Tagging:** Enemies that receive the invisibility effect are tagged with "biome_modifier_effect" to prevent repeated application.
*   **Self-Destruction:** The invisibility machine entity is destroyed after its effect is applied.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()

local targets = EntityGetWithTag( "enemy" )
if ( #targets > 0 ) then
	for i,v in ipairs( targets ) do
		if ( EntityHasTag( v, "biome_modifier_effect" ) == false ) then
			local game_effect_comp = GetGameEffectLoadTo( v, "INVISIBILITY", true )
			if ( game_effect_comp ~= nil ) then
				ComponentSetValue2( game_effect_comp, "frames", -1 )
			end
			
			EntityAddTag( v, "biome_modifier_effect" )
		end
	end
	
	EntityKill( entity_id )
end
```