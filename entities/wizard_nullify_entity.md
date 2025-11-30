---
title: Wizard Nullify Entity
category: entities
---

# Wizard Nullify Entity

This entity represents a special boss wizard that has a unique "nullify" ability. When damaged, it can neutralize nearby projectiles and undergoes transformations based on its health.

## Core Functionality

The primary function of this entity is its `damage_received` callback. This function handles:

*   **Projectile Nullification:** When the wizard takes damage, it scans for nearby projectiles. If found, it disables their explosion effects and destroys them, spawning a `neutralized_tiny.xml` particle effect.
*   **Health-Based Transformations:** As the wizard's health drops below certain thresholds, it changes its "mode" and alters its visual components.

## Key Attributes and Behaviors

### Projectile Nullification

*   **Radius:** The wizard nullifies projectiles within a radius of **36 units**.
*   **Exclusions:** The wizard does not nullify the projectile that is currently damaging it or the projectile that caused the damage event.
*   **Effect:** Projectiles that are nullified have their `on_death_explode` and `on_lifetime_out_explode` components set to "0", effectively disabling explosions. A `neutralized_tiny.xml` particle effect is spawned at the projectile's location.

### Health-Based Transformations

The wizard has three distinct modes, controlled by a `VariableStorageComponent` with the tag `boss_wizard_mode`.

*   **Mode 0 (Initial):** The wizard's default state.
*   **Mode 1 (Below 50% HP):**
    *   The wizard's helmet components are disabled (`helmet` tag).
    *   Head components are enabled (`head` tag).
    *   A `blood_explosion.xml` particle effect is spawned above the wizard.
*   **Mode 2 (Below 20% HP):**
    *   Hand components are disabled (`hand` tag).
    *   Head components are disabled (`head` tag).
    *   End components are enabled (`end` tag).
    *   A `blood_explosion.xml` particle effect is spawned above the wizard.
    *   The `HotspotComponent`'s `sprite_hotspot_name` is set to "shoot_pos", likely altering its firing origin.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

function damage_received( damage, desc, entity_who_caused, is_fatal, proj_id )
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	
	-- Scan for nearby projectiles to nullify
	local projs = EntityGetInRadiusWithTag( x, y, 36, "projectile" )
	
	for i,projectile_id in ipairs( projs ) do
		-- Ensure it's not the projectile that hit the wizard
		if ( projectile_id ~= entity_who_caused ) and ( projectile_id ~= proj_id ) then
			local px,py = EntityGetTransform( projectile_id )
			local projectilecomponents = EntityGetComponent( projectile_id, "ProjectileComponent" )
			
			if ( projectilecomponents ~= nil ) then
				for j,comp_id in ipairs(projectilecomponents) do
					-- Disable explosion effects
					ComponentSetValue( comp_id, "on_death_explode", "0" )
					ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" )
				end
			end
			
			-- Spawn neutralization particle and kill projectile
			EntityLoad("data/entities/particles/neutralized_tiny.xml", px, py)
			EntityKill( projectile_id )
		end
	end
	
	-- Handle health-based transformations
	local comp = EntityGetFirstComponent( entity_id, "DamageModelComponent" )
	local comp2 = EntityGetFirstComponent( entity_id, "VariableStorageComponent", "boss_wizard_mode" )
	if ( comp ~= nil ) and ( comp2 ~= nil ) then
		local hp = ComponentGetValue2( comp, "hp" )
		local max_hp = ComponentGetValue2( comp, "max_hp" )
		local mode = ComponentGetValue2( comp2, "value_int" )
		
		-- Transition to Mode 1 (below 50% HP)
		if ( hp / max_hp < 0.5 ) and ( mode == 0 ) then
			mode = 1
			EntitySetComponentsWithTagEnabled( entity_id, "helmet", false )
			EntitySetComponentsWithTagEnabled( entity_id, "head", true )
			EntityLoad( "data/entities/particles/blood_explosion.xml", x, y - 40 )
		-- Transition to Mode 2 (below 20% HP)
		elseif ( hp / max_hp < 0.2 ) and ( mode == 1 ) then
			mode = 2
			EntitySetComponentsWithTagEnabled( entity_id, "hand", false )
			EntitySetComponentsWithTagEnabled( entity_id, "head", false )
			EntitySetComponentsWithTagEnabled( entity_id, "end", true )
			EntityLoad( "data/entities/particles/blood_explosion.xml", x, y - 20 )
			
			-- Adjust hotspot for shooting
			local hcomp = EntityGetFirstComponent( entity_id, "HotspotComponent" )
			if ( hcomp ~= nil ) then
				ComponentSetValue2( hcomp, "sprite_hotspot_name", "shoot_pos" )
			end
		end
		
		-- Update the wizard's mode
		ComponentSetValue2( comp2, "value_int", mode )
	end
end
```