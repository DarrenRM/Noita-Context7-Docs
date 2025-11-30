---
title: Essence to Power Projectile Modifier
category: scripts
---

---

# Essence to Power Projectile Modifier

This script modifies projectile behavior, specifically enhancing damage and explosion properties based on nearby "essence" targets. It aims to convert collected essence into raw power for the projectile.

## Core Functionality

The script identifies nearby projectiles tagged with "homing_target" or "summon_player". It then iterates through these projectiles, calculating a "count" based on their `max_hp` (damage). This "count" is used to:

*   Increase the projectile's base `damage`.
*   Increase the `damage` of its explosion.
*   Increase the `explosion_radius`.
*   Spawn particle effects with a count proportional to the collected essence.

## Key Attributes and Elements

### Projectile Identification

*   **`radius`**: The search radius (160 units) for nearby projectiles.
*   **`homing_target` tag**: Identifies projectiles that can be targeted for essence collection.
*   **`summon_player` tag**: Identifies projectiles that can also be targeted.

### Essence Calculation

*   **`max_hp`**: The `DamageModelComponent`'s `max_hp` attribute on a target projectile is used to determine its contribution to the "count".
*   **`count`**: A cumulative value derived from the `max_hp` of nearby essence targets. It's calculated as `math.max(0.5, amount * 0.25)`.
*   **`essence_to_power_target` tag**: Applied to projectiles that have already contributed their essence to prevent double-counting.

### Damage and Explosion Modification

*   **`ProjectileComponent`**: The primary component of the projectile being modified.
    *   **`mWhoShot`**: Identifies the entity that fired the projectile, used to avoid self-targeting.
    *   **`damage`**: The base damage of the projectile.
    *   **`config_explosion`**: A table containing explosion properties.
        *   **`damage`**: The damage dealt by the projectile's explosion.
        *   **`explosion_radius`**: The radius of the explosion.

### Enhancement Logic

*   **Damage Increase**: `damage = damage + math.min(120, count * 0.25)`
*   **Explosion Damage Increase**: `expdamage = expdamage + math.min(120, count * 0.25)`
*   **Explosion Radius Increase**: `exprad = math.max(exprad, math.min(120, math.floor(exprad + math.log(count * 5.5))))`

### Visual Effects

*   **`tinyspark_blue_large.xml`**: A particle effect entity loaded at the projectile's root.
*   **`ParticleEmitterComponent`**: The component of the particle effect.
    *   **`count_min`**: Minimum number of particles, capped by `math.min(math.floor(count * 0.5), 100)`.
    *   **`count_max`**: Maximum number of particles, capped by `math.min(count + 1, 120)`.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local root_id = EntityGetRootEntity( entity_id )
local x, y = EntityGetTransform( entity_id )
local radius = 160 -- Search radius for essence targets

-- Find nearby projectiles with specific tags
local projectiles = EntityGetInRadiusWithTag( x, y, radius, "homing_target" )
local projectiles2 = EntityGetInRadiusWithTag( x, y, radius, "summon_player" )

-- Combine projectile lists
if ( #projectiles2 > 0 ) then
	for i,v in ipairs( projectiles2 ) do
		table.insert( projectiles, v )
	end
end

local count = 0 -- Accumulator for essence power
local who_shot
local comp = EntityGetFirstComponent( entity_id, "ProjectileComponent" )

if ( comp ~= nil ) then
	who_shot = ComponentGetValue2( comp, "mWhoShot" ) -- Get the shooter to avoid self-targeting
end

if ( who_shot ~= nil ) and ( comp ~= nil ) then
	-- Iterate through identified projectiles
	for i,projectile_id in ipairs(projectiles) do
		-- Ensure it's not the projectile itself, its root, or the shooter, and hasn't been tagged yet
		if ( projectile_id ~= root_id ) and ( projectile_id ~= entity_id ) and ( projectile_id ~= who_shot ) and ( EntityHasTag( projectile_id, "essence_to_power_target" ) == false ) then
			local comp2 = EntityGetFirstComponent( projectile_id, "DamageModelComponent" )
			
			if ( comp2 ~= nil ) then
				local amount = ComponentGetValue2( comp2, "max_hp" ) or 0.1 -- Get target's HP (essence value)
				
				-- Calculate essence contribution
				count = count + math.max( 0.5, amount * 0.25 )
				
				EntityAddTag( projectile_id, "essence_to_power_target" ) -- Mark as processed
				local eid = EntityLoad( "data/entities/misc/essence_to_power_cooldown.xml", x, y ) -- Load cooldown entity
				EntityAddChild( projectile_id, eid ) -- Attach cooldown to target
			end
		end
	end
	
	-- Get current projectile stats
	local damage = ComponentGetValue2( comp, "damage" )
	local expdamage = ComponentObjectGetValue( comp, "config_explosion", "damage" )
	local exprad = ComponentObjectGetValue( comp, "config_explosion", "explosion_radius" )
	
	-- Apply enhancements based on collected essence
	damage = damage + math.min( 120, count * 0.25 )
	expdamage = expdamage + math.min( 120, count * 0.25 )
	exprad = math.max( exprad,  math.min( 120, math.floor( exprad + math.log( count * 5.5 ) ) ) )
	
	-- Update projectile stats
	ComponentSetValue2( comp, "damage", damage )
	ComponentObjectSetValue( comp, "config_explosion", "damage", expdamage )
	ComponentObjectSetValue( comp, "config_explosion", "explosion_radius", exprad )
	
	-- Load and configure particle effect
	local effect_id = EntityLoad("data/entities/particles/tinyspark_blue_large.xml", x, y)
	EntityAddChild( root_id, effect_id )
	
	edit_component( effect_id, "ParticleEmitterComponent", function(comp3,vars)
		local part_min = math.min( math.floor( count * 0.5 ), 100 )
		local part_max = math.min( count + 1, 120 )
		
		ComponentSetValue2( comp3, "count_min", part_min )
		ComponentSetValue2( comp3, "count_max", part_max )
	end)
end