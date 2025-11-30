---
title: Boss Spirit Orb Effect
category: entities
---

---

# Boss Spirit Orb Effect

This entity script defines the behavior of an orb effect associated with the boss spirit in Noita. When activated, it targets nearby "hittable" entities, reduces their health, and spawns a blue glow particle effect.

## Key Functionality

*   **Targeting:** Identifies entities within a 40-unit radius that possess the "hittable" tag.
*   **Health Reduction:** For each targeted entity, it accesses its `DamageModelComponent`. If the entity is not tagged as "islandspirit" and has more than 0.04 HP, its HP is halved.
*   **Particle Spawning:** Spawns a `blue_glow.xml` particle effect at the location of each targeted entity.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )

-- Find all entities within a 40-unit radius with the "hittable" tag
local entities = EntityGetInRadiusWithTag( x, y, 40, "hittable" )

for i,v in ipairs( entities ) do
	-- Get the DamageModelComponent for the entity
	local comp = EntityGetFirstComponent( v, "DamageModelComponent" )
	
	-- Check if the component exists and the entity is not a boss spirit
	if ( comp ~= nil ) and ( EntityHasTag( v, "islandspirit" ) == false ) then
		local hp = ComponentGetValue2( comp, "hp" )
		-- Halve HP if it's above a certain threshold
		if ( hp > 0.04 ) then
			hp = hp * 0.5
		end
		ComponentSetValue2( comp, "hp", hp )
	end
	
	-- Spawn a blue glow particle effect at the entity's location
	local ex,ey = EntityGetTransform( v )
	EntityLoad( "data/entities/particles/blue_glow.xml", ex, ey )
end
```

## Key Components and Attributes

*   **`EntityGetInRadiusWithTag(x, y, radius, tag)`**: A utility function to find entities within a specified radius and with a given tag.
*   **`DamageModelComponent`**: The component responsible for managing an entity's health.
*   **`ComponentGetValue2(component, "hp")`**: Retrieves the current HP value from a `DamageModelComponent`.
*   **`ComponentSetValue2(component, "hp", value)`**: Sets the HP value for a `DamageModelComponent`.
*   **`EntityHasTag(entity, tag)`**: Checks if an entity possesses a specific tag.
*   **`EntityLoad(filepath, x, y)`**: Loads and spawns an entity from an XML file at the given coordinates.
*   **`"hittable"` tag**: A tag used to identify entities that can be affected by this orb effect.
*   **`"islandspirit"` tag**: A tag used to exclude boss spirits from being affected by this orb effect.
*   **`data/entities/particles/blue_glow.xml`**: The particle effect spawned by this orb.