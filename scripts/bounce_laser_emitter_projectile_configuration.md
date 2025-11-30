---
title: Bounce Laser Emitter Projectile Configuration
category: scripts
---

---

# Bounce Laser Emitter Projectile Configuration

This script modifies the behavior of a projectile, specifically a "bounce laser emitter," by defining its visual effect upon bouncing.

## Key Functionality

The primary purpose of this script is to set the visual effect that plays when the projectile bounces.

### `bounce_fx_file`

This attribute within the `ProjectileComponent` determines the particle effect or entity that is spawned when the projectile bounces off a surface.

*   **Value:** `data/entities/projectiles/deck/orb_laseremitter_weak_opposite.xml`
    *   This points to a specific XML file that defines the visual appearance of the bounce effect.

## Script Logic

The script first retrieves the entity ID and its parent entity ID. It then checks if the projectile has a parent. Based on this, it identifies the `target_id` to which the `ProjectileComponent` belongs. If a `ProjectileComponent` is found, it modifies the `bounce_fx_file` attribute.

```lua
-- Retrieve the entity ID and its transform
local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

-- Get the parent entity ID
local parent_id = EntityGetParent( entity_id )

local target_id = 0

-- Determine the target entity for component modification
if ( parent_id ~= NULL_ENTITY ) then
	target_id = parent_id
else
	target_id = entity_id
end

-- Check if a target entity was found and has a ProjectileComponent
if ( target_id ~= NULL_ENTITY ) then
	local projectile_components = EntityGetComponent( target_id, "ProjectileComponent" )
	
	if( projectile_components == nil ) then return end -- Exit if no ProjectileComponent
	
	-- Modify the ProjectileComponent if it exists
	if ( #projectile_components > 0 ) then
		edit_component( target_id, "ProjectileComponent", function(comp,vars)
			-- Set the bounce effect file
			vars.bounce_fx_file = "data/entities/projectiles/deck/orb_laseremitter_weak_opposite.xml"
		end)
	end
end
```