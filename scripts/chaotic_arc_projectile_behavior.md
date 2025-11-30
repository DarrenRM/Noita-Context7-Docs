---
title: Chaotic Arc Projectile Behavior
category: scripts
---

---

# Chaotic Arc Projectile Behavior

This script modifies the velocity of a projectile, introducing a chaotic, randomized adjustment to its trajectory.

## Key Attributes

### Velocity Component Modification

The script targets the `VelocityComponent` of the projectile entity.

*   **Randomized Velocity Adjustment**:
    *   It calculates a `scale` based on the projectile's current velocity magnitude.
    *   A `random_adjustment` is generated within the range of `[-scale, scale]`.
    *   This adjustment is then added to both the X and Y components of the projectile's velocity, causing it to deviate from its intended path.

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

edit_component( entity_id, "VelocityComponent", function(comp,vars)
	local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")
	
	-- Scale of random adjustment is proportional to current velocity
	local scale = math.max( math.abs( vel_x ), math.abs( vel_y ) ) * 0.4
	local random_adjustment = Random( 0 - scale, scale )

	-- Apply random adjustment to velocity
	vel_x = vel_x + random_adjustment
	vel_y = vel_y + random_adjustment

	ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)
end)
```