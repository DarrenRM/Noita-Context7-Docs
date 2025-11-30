---
title: Contact Damage Perk
category: scripts
---

---

# Contact Damage Perk

This script implements a perk that causes entities to deal increasing damage to the player based on how close they are to death.

## Key Components

### Damage Calculation

The core logic calculates damage based on the entity's current health (`hp`) relative to its maximum health (`max_hp`).

*   **Multiplier:** `1 - (hp / max_hp)`
    *   This value ranges from 0 (full health) to 1 (near death).
*   **Damage per Frame:** `0.04 + 0.15 * multiplier`
    *   This formula ensures that as the entity's health decreases, the damage it deals per frame increases.

### Entity Interaction

The script targets the `DamageModelComponent` of the root entity (likely the player) and the `AreaDamageComponent` of the entity itself.

*   **`DamageModelComponent`**: Used to retrieve the entity's current and maximum health.
*   **`AreaDamageComponent`**: Used to set the calculated `damage_per_frame`.

## Lua Script Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local root_id    = EntityGetRootEntity( entity_id )
local pos_x, pos_y = EntityGetTransform( entity_id )

if ( entity_id ~= root_id ) then
	local comp = EntityGetFirstComponent( root_id, "DamageModelComponent" )
	local comp2 = EntityGetFirstComponent( entity_id, "AreaDamageComponent" )
	
	if ( comp ~= nil ) and ( comp2 ~= nil ) then
		local hp = ComponentGetValue2( comp, "hp" )
		local max_hp = ComponentGetValue2( comp, "max_hp" )
		
		local multiplier = 1 - ( hp / max_hp )
		local damage = 0.04 + 0.15 * multiplier
		
		ComponentSetValue2( comp2, "damage_per_frame", damage )
	end
end