---
title: Horizontal Arc Projectile Velocity
category: scripts/
---

# Horizontal Arc Projectile Velocity

This script modifies the velocity of a projectile to ensure it travels horizontally.

## Key Attributes

### VelocityComponent Modification

This script targets the `VelocityComponent` of an entity.

*   **`mVelocity`**: The primary attribute modified is the `mVelocity` vector.
    *   The `vel_x` component of the velocity is preserved.
    *   The `vel_y` component is explicitly set to `0`, enforcing horizontal movement.

## Lua Script

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

edit_component( entity_id, "VelocityComponent", function(comp,vars)
	local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")

	vel_x = vel_x
	vel_y = 0

	ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)
end)
```