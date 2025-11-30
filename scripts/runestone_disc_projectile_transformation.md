---
title: Runestone Disc Projectile Transformation
category: scripts
---

# Runestone Disc Projectile Transformation

This script defines the behavior of the "Runestone Disc" item in Noita, specifically how it interacts with and transforms other projectiles. When a Runestone Disc is active, it targets nearby projectiles that are *not* already "disc_bullet" projectiles. Upon detection, it modifies these projectiles by disabling their explosion on death and on lifetime expiration. It then replaces the original projectile with a "disc_bullet" projectile originating from the same position and with the same velocity. Finally, the original projectile is destroyed.

## Key Functionality

### Projectile Detection and Filtering
- Detects projectiles within a 192-unit radius.
- Filters out projectiles that already have the "disc_bullet" tag.

### Projectile Modification
- Disables `on_death_explode` for detected projectiles.
- Disables `on_lifetime_out_explode` for detected projectiles.

### Projectile Replacement
- Shoots a new projectile of type `data/entities/projectiles/deck/disc_bullet.xml`.
- The new projectile inherits the position and velocity of the original projectile.

### Projectile Destruction
- The original, modified projectile is destroyed after being replaced.

## Core Components and Logic

The script primarily utilizes the following Noita API functions and concepts:

### Entity Management
- `GetUpdatedEntityID()`: Retrieves the ID of the entity running the script.
- `EntityGetTransform( entity_id )`: Gets the position (x, y) of an entity.
- `EntityGetInRadiusWithTag( x, y, radius, tag )`: Finds entities within a specified radius and with a given tag.
- `EntityGetTags( entity_id )`: Retrieves the tags associated with an entity.
- `EntityGetComponent( entity_id, component_name )`: Gets all components of a specific type attached to an entity.
- `ComponentSetValue( component_id, property_name, value )`: Sets a value for a specific property of a component.
- `ComponentGetValueVector2( component_id, property_name, default_x, default_y )`: Retrieves a 2D vector value from a component.
- `shoot_projectile_from_projectile( projectile_id, projectile_xml, x, y, vel_x, vel_y )`: Shoots a new projectile from an existing one.
- `EntityKill( entity_id )`: Destroys an entity.

### Velocity Handling
- `VelocityComponent`: A component that defines the velocity of an entity. The script specifically targets its `mVelocity` property.

### Conditional Logic
- `if ( #projectiles > 0 ) then ... end`: Checks if any projectiles were found.
- `if ( tags == nil ) or ( string.find( tags, "disc_bullet" ) == nil ) then ... end`: Ensures the projectile is not already a "disc_bullet".

## Example Usage (Conceptual)

Imagine a scenario where the player has the Runestone Disc active. If a standard enemy projectile (e.g., a basic bullet) flies near the player, this script will intercept it. The bullet will stop exploding on impact or when its time runs out, and instead, it will be replaced by a "disc_bullet" projectile, effectively changing the projectile's behavior mid-flight.

```lua
-- Example snippet demonstrating projectile detection and modification
local projectiles = EntityGetInRadiusWithTag( x, y, 192, "projectile" )
if ( #projectiles > 0 ) then
	for i,projectile_id in ipairs( projectiles ) do
		local tags = EntityGetTags( projectile_id )
		
		-- Check if it's not a disc_bullet already
		if ( tags == nil ) or ( string.find( tags, "disc_bullet" ) == nil ) then
			local px, py = EntityGetTransform( projectile_id )
			local vel_x, vel_y = 0,0
			
			-- Get components to modify explosion behavior
			local projectilecomponents = EntityGetComponent( projectile_id, "ProjectileComponent" )
			if ( projectilecomponents ~= nil ) then
				for j,comp_id in ipairs( projectilecomponents ) do
					ComponentSetValue( comp_id, "on_death_explode", "0" )
					ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" )
				end
			end
			
			-- Get velocity to transfer
			local velocitycomponents = EntityGetComponent( projectile_id, "VelocityComponent" )
			if ( velocitycomponents ~= nil ) then
				edit_component( projectile_id, "VelocityComponent", function(comp,vars)
					vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity", vel_x, vel_y)
				end)
			end
			
			-- Replace with disc_bullet and kill original
			shoot_projectile_from_projectile( projectile_id, "data/entities/projectiles/deck/disc_bullet.xml", px, py, vel_x, vel_y )
			EntityKill( projectile_id )
		end
	end
end
```