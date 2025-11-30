---
title: Boss Wizard Orb Spawning
category: entities
---

# Boss Wizard Orb Spawning

This script handles the spawning of orbs associated with the boss wizard. It creates a series of orbs, alternating between "blood" and "death" types, and assigns them a unique ID.

## Key Functionality

*   **Orb Spawning Loop:** Iterates 8 times to spawn multiple orbs.
*   **Alternating Orb Types:** Spawns `wizard_orb_blood.xml` for even iterations and `wizard_orb_death.xml` for odd iterations.
*   **Entity Loading:** Uses `EntityLoad` to instantiate the orb entities.
*   **Parenting:** Attaches spawned orbs as children to the boss wizard entity using `EntityAddChild`.
*   **Variable Storage:** Assigns a unique integer ID (0-7) to each orb via a `VariableStorageComponent` named `wizard_orb_id`.

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )

for i=1,8 do
	local eid
	
	if ( i % 2 == 0 ) then
		eid = EntityLoad( "data/entities/animals/boss_wizard/wizard_orb_blood.xml", x, y )
	else
		eid = EntityLoad( "data/entities/animals/boss_wizard/wizard_orb_death.xml", x, y )
	end
	
	if ( eid ~= nil ) then
		EntityAddChild( entity_id, eid )
		
		local comp = EntityGetFirstComponent( eid, "VariableStorageComponent", "wizard_orb_id" )
		if ( comp ~= nil ) then
			ComponentSetValue2( comp, "value_int", i-1 )
		end
	end
end
```