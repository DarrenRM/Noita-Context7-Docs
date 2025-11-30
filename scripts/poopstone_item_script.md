---
title: Poopstone Item Script
category: scripts
---

# Poopstone Item Script

This script defines the behavior of the "Poopstone" item in Noita. When used, it applies various status effects to nearby enemies.

## Key Functionality

The primary function of this script is to detect and affect enemies within a certain radius.

### Target Detection

*   **Radius:** Enemies within `160` units of the Poopstone are targeted.
*   **Tag:** Targets entities with the `"enemy"` tag.
*   **Immunity Check:** Enemies with the `"poopstone_immunity"` tag are ignored.

### Applied Effects

For each eligible enemy, the following effects are applied:

*   **Stains:** `EntityAddRandomStains( eid, CellFactory_GetType("poo"), 10 )` applies "poo" stains with a magnitude of `10`.
*   **Game Effects:** The script attempts to apply and extend the duration of several game effects:
    *   `FOOD_POISONING`: Duration set to `300` frames.
    *   `POISON`: Duration set to `300` frames.
    *   `SLIMY`: Duration set to `300` frames.

## Code Structure

```lua
local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local targets = EntityGetInRadiusWithTag( x, y, 160, "enemy" )

for i,eid in pairs( targets ) do
	if ( EntityHasTag( eid, "poopstone_immunity" ) == false ) then
		EntityAddRandomStains( eid, CellFactory_GetType("poo"), 10 )
		local e1c,e1e = GetGameEffectLoadTo( eid, "FOOD_POISONING", false )
		local e2c,e2e = GetGameEffectLoadTo( eid, "POISON", false )
		local e3c,e3e = GetGameEffectLoadTo( eid, "SLIMY", false )

		if ( e1c ~= nil ) and ( e1e ~= nil ) then
			ComponentSetValue2( e1c, "frames", 300 )
		end

		if ( e2c ~= nil ) and ( e2e ~= nil ) then
			ComponentSetValue2( e2c, "frames", 300 )
		end

		if ( e3c ~= nil ) and ( e3e ~= nil ) then
			ComponentSetValue2( e3c, "frames", 300 )
		end
	end
end
```