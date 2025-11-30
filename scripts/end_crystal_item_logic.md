---
title: End Crystal Item Logic
category: scripts
---

# End Crystal Item Logic

This script defines the behavior when the End Crystal item is picked up by a player.

## Core Functionality

The `item_pickup` function handles the logic executed when the End Crystal is collected.

### Key Actions:

1.  **Display Message:**
    *   Logs an important message to the player using `$log_endcrystal` and `$logdesc_endcrystal`.

2.  **Full Heal:**
    *   Iterates through all `DamageModelComponent` components attached to the player entity.
    *   For each component, it sets the current `hp` to the `max_hp`, effectively healing the player to full health.

3.  **Spawn Boss Entity:**
    *   Loads and spawns the `boss_dragon_endcrystal.xml` entity at a position relative to the player's current location.

4.  **Particle Effect:**
    *   Spawns a `main_pink.xml` particle effect at the player's location.

5.  **Screen Shake:**
    *   Initiates a screen shake with an intensity of 40.

6.  **Destroy Item:**
    *   Removes the End Crystal item entity from the game.

### Code Snippet:

```lua
function item_pickup( entity_item, entity_who_picked, name )
	GamePrintImportant( "$log_endcrystal", "$logdesc_endcrystal" )
	
	local damagemodels = EntityGetComponent( entity_who_picked, "DamageModelComponent" )

	local max_hp = 0
	
	if( damagemodels ~= nil ) then
		for i,v in ipairs(damagemodels) do
			max_hp = tonumber( ComponentGetValue( v, "max_hp" ) )
			ComponentSetValue( v, "hp", max_hp)
		end
	end

	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	EntityLoad( "data/entities/animals/ending_placeholder/boss_dragon_endcrystal.xml", x, y - 256 )
	EntityLoad( "data/entities/particles/particle_explosion/main_pink.xml", x, y )
	GameScreenshake( 40 )
	EntityKill( entity_item )
end
```