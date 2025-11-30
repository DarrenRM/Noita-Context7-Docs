---
title: Orb Blood Damage Component
category: entities
---

# Orb Blood Damage Component

This script defines the behavior for an entity that inflicts curse damage when it receives damage. It's designed to be attached to entities that act as a source of "blood damage" or similar curse-based attacks.

## Key Functionality

### `damage_received(dmg, msg, source)`

This function is called when the entity receives damage.

*   **`dmg`**: The amount of damage received.
*   **`msg`**: A message string associated with the damage.
*   **`source`**: The entity ID of the source that inflicted the damage.

#### Behavior:

1.  **Identify Source**: It checks if the damage source is valid (not nil, not the entity itself, and not its root entity).
2.  **Inflict Curse Damage**: If a valid source is found, it inflicts curse damage back onto the `source` entity.
    *   The damage type is `DAMAGE_CURSE`.
    *   The damage message is localized as `$damage_orb_blood`.
    *   The damage effect is `DISINTEGRATED`.
    *   The damage amount is the same as the damage received (`dmg`).
3.  **Self-Heal**: After potentially inflicting damage, the entity fully heals itself by setting its current HP to its maximum HP.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

function damage_received( dmg, msg, source )
	local entity_id = GetUpdatedEntityID()
	local root_id = EntityGetRootEntity( entity_id )
	local x,y = EntityGetTransform( root_id )
	
	if ( source ~= nil ) and ( source ~= NULL_ENTITY ) and ( source ~= entity_id ) and ( source ~= root_id ) then
		local hm = EntityGetTransform( source )
		
		if ( hm ~= nil ) then
			-- Inflict curse damage back to the source
			EntityInflictDamage( source, dmg, "DAMAGE_CURSE", "$damage_orb_blood", "DISINTEGRATED", 0, 0, entity_id )
		end
	else
		-- This section is commented out and appears to be a fallback for when the source is not clearly defined,
		-- potentially to damage the player if the source is unclear.
		--[[
		local pls = EntityGetInRadiusWithTag( x, y, 160, "player_unit" )
		if ( #pls > 0 ) then
			local pl = pls[1]
			
			EntityInflictDamage( pl, dmg, "DAMAGE_CURSE", "$damage_orb_blood", "DISINTEGRATED", 0, 0, entity_id )
		end
		]]--
	end
	
	-- Heal the entity to full HP
	local comp = EntityGetFirstComponent( entity_id, "DamageModelComponent" )
	if ( comp ~= nil ) then
		local max_hp = ComponentGetValue2( comp, "max_hp" )
		ComponentSetValue2( comp, "hp", max_hp )
	end
end
```