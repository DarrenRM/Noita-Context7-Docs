---
title: Boss Fish Movement
category: entities
---

---

# Boss Fish Movement

This document describes the movement behavior of the Boss Fish entity in Noita, as defined in `movement.lua`.

## Core Movement Logic

The Boss Fish's movement is primarily controlled by its `VelocityComponent`. The velocity is dynamically calculated based on the game frame number, creating a cyclical and somewhat predictable movement pattern.

### Velocity Component

The `VelocityComponent` is modified to set the `mVelocity` vector.

```lua
edit_component( entity_id, "VelocityComponent", function(comp,vars)
	local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")

	-- Horizontal velocity is determined by the cosine of an angle derived from the game frame number.
	vel_x = math.cos( angle ) * 25

	-- Vertical velocity is determined by the cosine of a different angle derived from the game frame number.
	vel_y = math.cos( angle2 ) * 15

	ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)
end)
```

### Movement Parameters

The movement is influenced by two key angle calculations:

*   **`angle`**: `( GameGetFrameNum() - 352 ) * 0.0081`
    *   This angle influences the horizontal velocity.
*   **`angle2`**: `( GameGetFrameNum() + 212 ) * 0.006`
    *   This angle influences the vertical velocity.

These calculations result in the Boss Fish oscillating horizontally and vertically with specific amplitudes and frequencies.