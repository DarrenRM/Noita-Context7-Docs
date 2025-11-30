---
title: Duck Projectile Behavior
category: scripts
---

# Duck Projectile Behavior

This script defines the behavior for a "duck" projectile in Noita, focusing on its homing capabilities and visual orientation.

## Key Attributes

### Homing Behavior

The duck projectile attempts to home in on targets tagged with "homing_target".

-   **Detection Radius**: The projectile searches for targets within a `radius` of 12 units.
-   **Targeting**: If any entities with the "homing_target" tag are found within the radius, the projectile's behavior changes.

### Collision Behavior

When a homing target is acquired, the projectile is set to die upon collision.

-   **`on_collision_die`**: Set to `true` for the `ProjectileComponent` when a homing target is detected.

### Visual Orientation

The projectile's sprite will flip horizontally to face its direction of movement.

-   **Sprite Flipping**: The `special_scale_x` property of the `SpriteComponent` is adjusted based on the projectile's horizontal velocity (`mVelocity.x`).
    -   If `vel_x > 0`, `special_scale_x` is set to `1` (facing right).
    -   If `vel_x < 0`, `special_scale_x` is set to `-1` (facing left).

### Timer Component

A `LuaComponent` with the ID "duck_timer" is present and configured to execute every frame.

-   **`execute_every_n_frame`**: Set to `1` for the "duck_timer" component.

## Lua Script Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )
local radius = 12

local projectiles = EntityGetInRadiusWithTag( x, y, radius, "homing_target" )
local comp = EntityGetFirstComponent( entity_id, "LuaComponent", "duck_timer" )

if ( comp ~= nil ) then
	ComponentSetValue2( comp, "execute_every_n_frame", 1 )
end

if ( #projectiles > 0 ) then
	local comp2 = EntityGetFirstComponent( entity_id, "ProjectileComponent" )
	if ( comp2 ~= nil ) then
		ComponentSetValue2( comp2, "on_collision_die", true )
	end
end

comp = EntityGetFirstComponent( entity_id, "SpriteComponent" )

if ( comp ~= nil ) then
	edit_component( entity_id, "VelocityComponent", function(vcomp,vars)
		local vel_x,vel_y = ComponentGetValueVector2( vcomp, "mVelocity")
		
		if ( vel_x > 0 ) then
			ComponentSetValue2( comp, "special_scale_x", 1 )
		elseif ( vel_x < 0 ) then
			ComponentSetValue2( comp, "special_scale_x", -1 )
		end
	end)
end
```