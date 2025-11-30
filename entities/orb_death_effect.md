---
title: Orb Death Effect
category: entities
---

# Orb Death Effect

This script defines the behavior for an effect that triggers when a "boss_wizard" entity is destroyed. It aims to apply a "protection_all_short_evil" effect to nearby "boss_wizard" entities that do not already possess a similar protection.

## Key Functionality

The script iterates through entities within a radius of 128 units around the dying "boss_wizard". For each identified "boss_wizard" target, it checks if any of its children have a "protection_all_short" component. If no such protection is found, a new "effect_protection_all_short_evil" entity is loaded and attached as a child to the target "boss_wizard".

## Core Logic

```lua
local entity_id = GetUpdatedEntityID() -- Gets the ID of the entity executing this script.
local x,y = EntityGetTransform( entity_id ) -- Retrieves the position of the entity.
local r = 128 -- Defines the radius for searching nearby entities.

-- Finds all entities with the "boss_wizard" tag within the specified radius.
local targets = EntityGetInRadiusWithTag( x, y, r, "boss_wizard" )

for i,v in ipairs( targets ) do
	-- Ensures the target is not the entity that is currently dying.
	if ( v ~= entity_id ) then
		local c = EntityGetAllChildren( v ) -- Gets all child entities of the target.
		local valid = true -- Flag to determine if the protection can be applied.
		
		if ( c ~= nil ) then
			for a,b in ipairs( c ) do
				-- Checks if any child entity has a "GameEffectComponent" with "protection_all_short".
				local comps = EntityGetComponent( b, "GameEffectComponent", "protection_all_short" )
				
				if ( comps ~= nil ) then
					valid = false -- If protection is found, mark as invalid.
					break
				end
			end
		end
		
		-- If no existing protection was found, apply the new effect.
		if valid then
			-- Loads and creates the "effect_protection_all_short_evil" entity at the target's position.
			local eid = EntityLoad( "data/entities/misc/effect_protection_all_short_evil.xml", x, y )
			EntityAddChild( v, eid ) -- Adds the new effect as a child to the target boss wizard.
		end
	end
end
```

## Key Entities and Components

*   **`boss_wizard`**: The primary entity type targeted by this script.
*   **`GameEffectComponent`**: A component used to manage game effects.
*   **`protection_all_short`**: A specific effect identifier checked for existing protection.
*   **`effect_protection_all_short_evil.xml`**: The entity loaded to apply the new protection effect.

## Parameters

| Parameter | Type   | Description                                                              |
| :-------- | :----- | :----------------------------------------------------------------------- |
| `r`       | Number | The radius (in pixels) within which to search for `boss_wizard` targets. |