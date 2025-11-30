---
title: Vacuum Powder Projectile
category: scripts
---

---

# Vacuum Powder Projectile

This script defines the behavior of the "Vacuum Powder" projectile in Noita. It's a projectile designed to inflict significant damage.

## Key Attributes

### Damage
- **Damage Amount**: 1000
- **Damage Type**: `DAMAGE_PROJECTILE`
- **Damage Source**: Implicitly the projectile itself.
- **Damage Effect**: `NONE` (no special visual or gameplay effect beyond damage).

### Entity Behavior
- **Kill Now**: The projectile is set to be destroyed immediately after its damage is applied (`kill_now = true`). This suggests it's a single-use, high-impact projectile.

## Lua Script Breakdown

```lua
dofile_once( "data/scripts/lib/utilities.lua" ) -- Loads utility functions.

local entity_id    = GetUpdatedEntityID() -- Gets the unique ID of the projectile entity.
local pos_x, pos_y = EntityGetTransform( entity_id ) -- Retrieves the projectile's position (though not directly used in this snippet).

local comp = EntityGetFirstComponent( entity_id, "DamageModelComponent" ) -- Finds the DamageModelComponent attached to the projectile.
if ( comp ~= nil ) then
	ComponentSetValue2( comp, "kill_now", true ) -- Sets the 'kill_now' property of the DamageModelComponent to true, ensuring the projectile is removed after its action.
end

EntityInflictDamage( entity_id, 1000, "DAMAGE_PROJECTILE", "", "NONE", 0, 0 ) -- Inflicts 1000 damage of type DAMAGE_PROJECTILE from the projectile's entity.
```