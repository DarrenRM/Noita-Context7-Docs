---
title: Runestone Fireball - Projectile Transformation
category: scripts
---

# Runestone Fireball - Projectile Transformation

This script defines the behavior of a runestone that transforms nearby projectiles into fireballs. When activated, it scans for projectiles within a certain radius and, if they are not already fireballs, it replaces them with a new fireball projectile originating from the same position and with the same velocity.

## Key Functionality

*   **Projectile Detection:** Scans for entities tagged as "projectile" within a 192-unit radius of the runestone.
*   **Fireball Check:** Identifies if a detected projectile is already a "fireball" based on its tags.
*   **Projectile Transformation:** If a projectile is not a fireball, it is replaced by a new "fireball.xml" projectile.
*   **Velocity Preservation:** The original projectile's velocity is captured and applied to the new fireball.
*   **Component Modification:** Disables explosion effects (`on_death_explode`, `on_lifetime_out_explode`) on the original projectile before it's destroyed.
*   **Entity Replacement:** The original projectile is destroyed and a new fireball is spawned.

## Core Logic

The script iterates through detected projectiles. For each projectile, it checks its tags. If the tags do not contain "fireball", the script proceeds to:

1.  Retrieve the projectile's current position and velocity.
2.  Modify the projectile's `ProjectileComponent` to disable death and lifetime-out explosions.
3.  Use `shoot_projectile_from_projectile` to spawn a new "fireball.xml" projectile at the original projectile's location and with its velocity.
4.  Destroy the original projectile using `EntityKill`.

## Key Components and Functions

*   `GetUpdatedEntityID()`: Gets the ID of the entity running the script.
*   `EntityGetTransform( entity_id )`: Retrieves the position (x, y) of an entity.
*   `EntityGetInRadiusWithTag( x, y, radius, tag )`: Finds entities within a specified radius and with a given tag.
*   `EntityGetTags( entity_id )`: Retrieves the tags associated with an entity.
*   `string.find( tags, "fireball" )`: Checks if the "fireball" string exists within the entity's tags.
*   `EntityGetComponent( entity_id, component_name )`: Retrieves components of a specific type from an entity.
*   `ComponentSetValue( component_id, property_name, value )`: Sets a value for a component property.
*   `edit_component( entity_id, component_name, callback_function )`: Allows modification of a component's properties using a callback.
*   `ComponentGetValueVector2( component, property_name, default_x, default_y )`: Retrieves a 2D vector value from a component.
*   `shoot_projectile_from_projectile( projectile_id, projectile_xml_path, x, y, vel_x, vel_y )`: Spawns a new projectile from an existing one.
*   `EntityKill( entity_id )`: Destroys an entity.

## Configuration Parameters

*   **Detection Radius:** `192` units.
*   **Projectile Type to Spawn:** `data/entities/projectiles/deck/fireball.xml`.
*   **Explosion Disabling:** `on_death_explode` and `on_lifetime_out_explode` are set to `"0"`.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local projectiles = EntityGetInRadiusWithTag( x, y, 192, "projectile" )
if ( #projectiles > 0 ) then
	for i,projectile_id in ipairs( projectiles ) do
		local tags = EntityGetTags( projectile_id )
		
		if ( tags == nil ) or ( string.find( tags, "fireball" ) == nil ) then
			local px, py = EntityGetTransform( projectile_id )
			local vel_x, vel_y = 0,0
			
			local projectilecomponents = EntityGetComponent( projectile_id, "ProjectileComponent" )
			local velocitycomponents = EntityGetComponent( projectile_id, "VelocityComponent" )
			
			if ( projectilecomponents ~= nil ) then
				for j,comp_id in ipairs( projectilecomponents ) do
					ComponentSetValue( comp_id, "on_death_explode", "0" )
					ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" )
				end
			end
			
			if ( velocitycomponents ~= nil ) then
				edit_component( projectile_id, "VelocityComponent", function(comp,vars)
					vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity", vel_x, vel_y)
				end)
			end
			
			shoot_projectile_from_projectile( projectile_id, "data/entities/projectiles/deck/fireball.xml", px, py, vel_x, vel_y )
			EntityKill( projectile_id )
		end
	end
end
```