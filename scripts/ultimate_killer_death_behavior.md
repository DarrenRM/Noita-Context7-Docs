---
title: Ultimate Killer Death Behavior
category: scripts
---

---

# Ultimate Killer Death Behavior

This script defines the behavior of the "Ultimate Killer" entity when it dies.

## Core Functionality

The primary function `death` is triggered when the Ultimate Killer entity is destroyed.

### Key Actions on Death:

*   **Explosion:** Spawns an `ultimate_killer_explosion.xml` projectile at the killer's location.
*   **Kill Counter:** Increments a global counter named `ULTIMATE_KILLER_KILLS`. This counter is capped at 25.

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

function death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	-- Spawn the explosion projectile
	shoot_projectile( entity_id, "data/entities/projectiles/ultimate_killer_explosion.xml", pos_x, pos_y, 0, 0 )
	
	-- Update the global kill counter
	local count = tonumber( GlobalsGetValue( "ULTIMATE_KILLER_KILLS", "0" ) )
	count = math.min( 25, count + 1 ) -- Cap at 25
	GlobalsSetValue( "ULTIMATE_KILLER_KILLS", tostring( count ) )
end
```