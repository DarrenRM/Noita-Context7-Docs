---
title: Expanding Orb Projectile
category: scripts
---

# Expanding Orb Projectile

This script defines the behavior of an expanding orb projectile in Noita. It dynamically adjusts its damage and visual radius over time, starting with maximum damage and radius and shrinking to minimum values.

## Key Attributes

### Projectile Behavior

*   **`execute_times`**: The total number of frames the projectile's expansion effect will last. (Default: 115)
*   **`damage_min`**: The minimum damage the projectile will deal. (Default: 0.1)
*   **`damage_max`**: The initial maximum damage the projectile will deal. This is dynamically set from the projectile's base damage.
*   **`radius_min`**: The minimum visual radius of the projectile's particle effect. (Default: 0)
*   **`radius_max`**: The initial maximum visual radius of the projectile's particle effect. This is dynamically set from the projectile's base damage.

### Dynamic Scaling

The script uses a linear interpolation (`lerp`) function to smoothly transition the projectile's damage and radius from their maximum to minimum values over the `execute_times` duration.

*   The `t` variable represents the current progress of the expansion, ranging from 0 to 1.
*   `current_damage` is calculated by interpolating between `damage_max` and `damage_min` based on `t`.
*   `current_radius` is calculated by interpolating between `radius_max` and `radius_min` based on `t`.

### Component Updates

*   **`ProjectileComponent`**: The `damage` and `collide_with_entities` properties of the projectile are updated in each execution frame to reflect the `current_damage` and ensure it interacts with entities.
*   **`ParticleEmitterComponent`**: The `area_circle_radius` property of the particle emitter is updated to visually represent the `current_radius`.

## Lua Code Snippet

```lua
dofile_once("data/scripts/lib/utilities.lua")

local execute_times = 115
local damage_min = 0.1
local damage_max = 1.8
local radius_min = 0
local radius_max = 8

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
local projectile_comp = EntityGetFirstComponent( entity_id, "ProjectileComponent" )
local storage_comp = get_variable_storage_component( entity_id, "base_damage" )
if projectile_comp == nil or storage_comp == nil then return end

local t = ComponentGetValue2( GetUpdatedComponentID(), "mTimesExecuted" )

-- store or recall base damage
if t == 0 then
	damage_max = ComponentGetValue2(projectile_comp, "damage")
	ComponentSetValue2(storage_comp, "value_float", damage_max)
else
	damage_max = ComponentGetValue2(storage_comp, "value_float")
end

t = t / execute_times -- 0...1
local current_damage = lerp(damage_max, damage_min, t)
local current_radius = lerp(radius_max, radius_min, t)

-- update damage & enable projectile collision
component_write( projectile_comp, { damage = current_damage, collide_with_entities = true } )

-- update visuals
local comp = EntityGetFirstComponent( entity_id, "ParticleEmitterComponent" )
ComponentSetValue2(comp, "area_circle_radius", current_radius, current_radius)
```