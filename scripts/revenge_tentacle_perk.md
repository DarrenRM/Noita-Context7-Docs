---
title: Revenge Tentacle Perk
category: scripts
---

# Revenge Tentacle Perk

This perk grants the player a defensive mechanism that retaliates when they take damage. Upon receiving damage, a tentacle projectile is fired towards the source of the damage.

## Core Functionality

The `damage_received` function is the primary handler for this perk. It triggers the tentacle projectile under specific conditions.

### Key Attributes & Logic

*   **Damage Threshold:** The perk only activates when positive damage is received (healing, indicated by `damage < 0`, is ignored).
*   **Self-Inflicted Damage Prevention:** The tentacle will not fire if the damage is self-inflicted or caused by the entity's parent.
*   **Cooldown:** A short cooldown of 2 frames (`script_wait_frames( entity_id, 2 )`) prevents rapid firing.
*   **Targeting:**
    *   If the damage source (`entity_who_caused`) is known and valid, the tentacle is aimed directly at it.
    *   If the damage source is unknown or invalid, a random angle is chosen.
*   **Projectile:** A specific projectile entity (`data/entities/misc/perks/revenge_tentacle_tentacle.xml`) is spawned.
*   **Velocity:** The tentacle projectile is launched with a significant velocity (`length = 900`), with a slight random deviation in angle.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

function damage_received( damage, desc, entity_who_caused, is_fatal )
	-- Get the ID of the entity that received damage
	local entity_id    = GetUpdatedEntityID()
	-- Get the position of the entity
	local x, y = EntityGetTransform( entity_id )
	
	-- Ignore healing damage
	if( damage < 0 ) then return end

	-- Set a random seed for consistent randomness
	SetRandomSeed( GameGetFrameNum(), x + y + entity_id )
	
	-- Prevent self-inflicted damage or damage from parent entity
	if ( entity_who_caused == entity_id ) or ( ( EntityGetParent( entity_id ) ~= NULL_ENTITY ) and ( entity_who_caused == EntityGetParent( entity_id ) ) ) then return end

	-- Implement a cooldown of 2 frames
	if script_wait_frames( entity_id, 2 ) then  return  end
	
	-- Initialize angle and velocity variables
	local angle = math.rad( Random( 1, 360 ) ) -- Default random angle
	local angle_random = math.rad( Random( -5, 5 ) ) -- Small random deviation
	local vel_x = 0
	local vel_y = 0
	local length = 900 -- Projectile speed
	
	-- If the damage source is valid, calculate the angle towards it
	if ( entity_who_caused ~= nil ) and ( entity_who_caused ~= NULL_ENTITY ) then
		local ex, ey = EntityGetTransform( entity_who_caused )
		
		if ( ex ~= nil ) and ( ey ~= nil ) then
			-- Calculate angle towards the damage source
			angle = 0 - math.atan2( ey - y, ex - x )
		end
	end
	
	-- Calculate the final velocity components
	vel_x = math.cos( angle + angle_random ) * length
	vel_y = 0- math.sin( angle + angle_random ) * length
	
	-- Shoot the tentacle projectile
	shoot_projectile( entity_id, "data/entities/misc/perks/revenge_tentacle_tentacle.xml", x, y, vel_x, vel_y )
end
```