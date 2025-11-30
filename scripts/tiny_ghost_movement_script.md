---
title: Tiny Ghost Movement Script
category: scripts
---

# Tiny Ghost Movement Script

This script defines the movement and animation behavior for the "Tiny Ghost" entity in Noita. It causes the ghost to float and bob around its parent entity, adjusting its animation based on its horizontal distance from the parent.

## Key Attributes and Behaviors

### Movement Logic

The script implements a smooth, interpolated movement towards a dynamically calculated target position.

*   **`lerp_amount`**: Controls the speed of interpolation. A value closer to 1 means slower movement.
*   **Target Calculation**: The target position is derived from the parent entity's transform, with a slight downward offset.
*   **Bobbing Effect**: The target position is further modified by sine waves, creating a bobbing motion both vertically (`bob_h`, `bob_speed_y`) and horizontally (`bob_w`, `bob_speed_x`).
*   **Randomization**: Small random variations are applied to timing and speeds to prevent multiple ghosts from moving identically.

### Animation Control

The script dynamically changes the ghost's animation state based on its horizontal position relative to its parent.

*   **Animation Modes**:
    *   `float_`: Used when the ghost is close to the parent.
    *   `fly_`: Used when the ghost is further away from the parent.
*   **Directional Animation**: The animation also changes based on the ghost's horizontal direction (left or right) relative to the parent.
*   **Animation Trigger**: The animation state is updated only if the current animation does not match the required mode and direction.

## Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

-- Movement parameters
local lerp_amount = 0.975 -- Interpolation speed (closer to 1 is slower)
local bob_h = 6           -- Vertical bobbing height
local bob_w = 20          -- Horizontal bobbing width
local bob_speed_y = 0.065 -- Vertical bobbing speed
local bob_speed_x = 0.01421 -- Horizontal bobbing speed

-- Get the entity's current transform
local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- If the entity is at origin (e.g., on spawn), get position from its parent
if pos_x == 0 and pos_y == 0 then
	pos_x, pos_y = EntityGetTransform(EntityGetParent(entity_id))
end

-- Calculate the target position for the ghost to follow
-- The target floats around the parent entity, slightly below it
local target_x, target_y = EntityGetTransform(EntityGetParent(entity_id))
if target_x == nil then return end -- Exit if parent is not found
target_y = target_y - 10 -- Offset target downwards

-- Get current frame number for procedural randomization
local time = GameGetFrameNum()
-- Generate a random value based on entity ID for unique behavior
local r = ProceduralRandomf(entity_id, 0, -1, 1)

-- Randomize timing and speeds slightly for individual ghost behavior
time = time + r * 10000
bob_speed_y = bob_speed_y + (r * bob_speed_y * 0.1)
bob_speed_x = bob_speed_x + (r * bob_speed_x * 0.1)
lerp_amount = lerp_amount - (r * lerp_amount * 0.01)

-- Apply bobbing effect to the target position
target_y = target_y + math.sin(time * bob_speed_y) * bob_h
target_x = target_x + math.sin(time * bob_speed_x) * bob_w

-- Calculate horizontal distance to parent for animation logic
local dist_x = pos_x - target_x

-- Smoothly move the ghost towards the calculated target position
pos_x,pos_y = vec_lerp(pos_x, pos_y, target_x, target_y, lerp_amount)
-- Update the entity's transform
EntitySetTransform( entity_id, pos_x, pos_y, 0, 1, 1)

-- Update the entity's sprite animation state
edit_component( entity_id, "SpriteComponent", function(comp,vars)
	local current_anim = ComponentGetValue( comp, "rect_animation")
	
	-- Determine animation mode based on horizontal distance
	local mode = "float_"
	if math.abs(dist_x) > 28 then mode = "fly_" end -- Switch to "fly_" if further than 28 units horizontally
	
	-- Check if animation needs to be changed based on current animation and heading
	if dist_x < 2 and current_anim ~= mode.."right" then
		-- If ghost is to the left of target and moving right, set "right" animation
		ComponentSetValue( comp, "rect_animation", mode.."right")
	elseif dist_x > 2 and current_anim ~= mode.."left" then
		-- If ghost is to the right of target and moving left, set "left" animation
		ComponentSetValue( comp, "rect_animation", mode.."left")
	end
end)
```