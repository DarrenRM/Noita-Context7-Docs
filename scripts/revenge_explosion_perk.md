---
title: Revenge Explosion Perk
category: scripts
---

# Revenge Explosion Perk

This script implements the "Revenge Explosion" perk in Noita. When the player takes damage, this perk triggers a small explosion originating from the player's entity.

## Core Functionality

The `damage_received` function is the primary handler for this perk. It's called whenever the player entity takes damage.

### Key Logic

*   **Damage Check:** The function first checks if the incoming `damage` is negative (which would indicate healing) and returns if it is.
*   **Self-Inflicted Damage Prevention:** It prevents the explosion from triggering if the damage was caused by the player themselves or their parent entity.
*   **Cooldown:** A cooldown mechanism (`script_wait_frames`) is implemented to prevent the explosion from firing too rapidly (every 5 frames).
*   **Projectile Spawning:** If the checks pass, it calls `shoot_projectile` to spawn an explosion entity (`data/entities/misc/perks/revenge_explosion.xml`) at the player's current position.
*   **Component Editing:** It then edits the spawned projectile's `ProjectileComponent` to:
    *   Set `mWhoShot` to the player's entity ID.
    *   Set `mShooterHerdId` to the player's herd ID (obtained from `GenomeDataComponent`).
    *   Configure the explosion to `dont_damage_this` entity (the player), preventing self-damage from the explosion.

## Associated Entity

The explosion itself is defined by the entity located at `data/entities/misc/perks/revenge_explosion.xml`. This XML file would contain the visual and physical properties of the explosion, such as its damage, radius, particle effects, etc.

```lua
dofile_once("data/scripts/lib/utilities.lua")

function damage_received( damage, desc, entity_who_caused, is_fatal )
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )
	
	if( damage < 0 ) then return end
	if ( entity_who_caused == entity_id ) or ( ( EntityGetParent( entity_id ) ~= NULL_ENTITY ) and ( entity_who_caused == EntityGetParent( entity_id ) ) ) then return end

	-- check that we're only shooting every 10 frames
	if script_wait_frames( entity_id, 5 ) then  return  end
	local eid = shoot_projectile( entity_id, "data/entities/misc/perks/revenge_explosion.xml", pos_x, pos_y, 0, 0 )
	
	local herd_id = -1
	edit_component( entity_id, "GenomeDataComponent", function(comp,vars)
		herd_id = ComponentGetValue2( comp, "herd_id" )
	end)
	
	edit_component( eid, "ProjectileComponent", function(comp,vars)
		ComponentSetValue2( comp, "mWhoShot", entity_id )
		ComponentSetValue2( comp, "mShooterHerdId", herd_id )
		
		ComponentObjectSetValue( comp, "config_explosion", "dont_damage_this", entity_id )
	end)
end
```