---
title: Add Homing Component to Projectiles
category: scripts
---

# Add Homing Component to Projectiles

This script adds a `HomingComponent` to projectiles when they are spawned. This allows projectiles to actively seek out targets.

## `shot` Function

This function is designed to be called when a projectile is created. It attaches the `HomingComponent` to the projectile entity.

### Key Attributes of `HomingComponent`

*   **`target_tag`**: (string) The tag of the entities that the projectile should home in on. In this example, it's set to `"prey"`.
*   **`homing_targeting_coeff`**: (string) Controls how strongly the projectile attempts to target. A higher value means more aggressive targeting. Set to `"36"` in this example.
*   **`detect_distance`**: (string) The radius within which the projectile will start seeking targets. Set to `"100"` in this example.
*   **`homing_velocity_multiplier`**: (string) A multiplier applied to the projectile's velocity when homing. Set to `"0.95"` in this example, meaning the homing velocity is slightly reduced from its base velocity.

### Example Usage

```lua
dofile_once("data/scripts/lib/utilities.lua")

function shot( projectile_id )
	EntityAddComponent( projectile_id, "HomingComponent",
	{
		target_tag="prey",
		homing_targeting_coeff="36",
		detect_distance="100",
		homing_velocity_multiplier="0.95",
	})
end
```