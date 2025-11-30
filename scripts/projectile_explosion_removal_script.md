---
title: Projectile Explosion Removal Script
category: scripts
---

# Projectile Explosion Removal Script

This script is designed to disable various explosion-related components on a projectile entity. It's useful for creating projectiles that should not detonate upon death, reaching their lifetime limit, or taking damage.

## Key Functionality

The script targets and modifies the following components to prevent explosions:

### ProjectileComponent

This component is edited to disable its built-in explosion triggers.

*   **`on_death_explode`**: Set to `"0"` to prevent explosion when the projectile is destroyed.
*   **`on_lifetime_out_explode`**: Set to `"0"` to prevent explosion when the projectile's lifetime expires.

### ExplosionComponent

All instances of `ExplosionComponent` attached to the projectile entity are disabled.

*   **`EntitySetComponentIsEnabled( entity_id, v, false )`**: This function is used to turn off each found `ExplosionComponent`.

### ExplodeOnDamageComponent

All instances of `ExplodeOnDamageComponent` attached to the projectile entity are disabled.

*   **`EntitySetComponentIsEnabled( entity_id, v, false )`**: This function is used to turn off each found `ExplodeOnDamageComponent`.

## Usage

This script should be attached to a projectile entity that you wish to prevent from exploding under normal circumstances.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

entity_id = EntityGetRootEntity( entity_id )

if ( entity_id ~= NULL_ENTITY ) then
	edit_component( entity_id, "ProjectileComponent", function(comp,vars)
		ComponentSetValue( comp, "on_death_explode", "0" )
		ComponentSetValue( comp, "on_lifetime_out_explode", "0" )
	end)
	
	local comps = EntityGetComponent( entity_id, "ExplosionComponent" )
	if ( comps ~= nil ) then
		for i,v in ipairs( comps ) do
			EntitySetComponentIsEnabled( entity_id, v, false )
		end
	end
	
	comps = EntityGetComponent( entity_id, "ExplodeOnDamageComponent" )
	if ( comps ~= nil ) then
		for i,v in ipairs( comps ) do
			EntitySetComponentIsEnabled( entity_id, v, false )
		end
	end
end
```