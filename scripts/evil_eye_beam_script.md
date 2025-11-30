---
title: Evil Eye Beam Script
category: scripts
---

# Evil Eye Beam Script

This script controls the behavior of the "Evil Eye Beam" item in Noita, specifically how it aims and emits its laser.

## Key Functionality

The script primarily focuses on:

*   **Beam Direction:** Determining the direction of the laser beam based on the item's movement or rotation.
*   **Iris Sprite:** Managing the visual representation of the "iris" that precedes the beam.
*   **Player Offset:** Adjusting the beam's trajectory to avoid hitting the player when moving quickly.
*   **Laser Emission:** Enabling the actual laser component of the item.

## Core Attributes & Logic

### Beam Direction Calculation

The script dynamically determines the beam's direction.

*   **Slow Movement/In Hand:** If the item is moving slowly or is held, the beam aligns with the item's rotation (`rot`).
*   **Fast Movement:** If the item is moving quickly, the beam's direction is derived from the item's velocity vector.
*   **Rotation Smoothing:** A `rot_lerp_amount` (0.25 or 0.15) is used to smoothly interpolate the beam's rotation, preventing jerky movements.

### Iris Sprite Management

The iris sprite is handled in a specific way to ensure it's always oriented correctly and appears in front of the beam.

*   **Positioning:** The iris is positioned slightly in front of the item along the calculated beam direction.
*   **Creation:** A new iris sprite is created using `GameCreateSpriteForXFrames` with the path `"data/items_gfx/evil_eye_iris.png"`.
*   **Disabling:** The original iris sprite within the entity is disabled after the script runs, relying on the newly created one.

### Player Velocity Offset

This logic prevents the laser from hitting the player when they are moving rapidly.

*   **Dot Product:** It calculates the dot product between the player's velocity and the beam's direction.
*   **Offset Amount:** A calculated `amount` (capped between 0 and 0.2) is applied to the player's velocity.
*   **Beam Adjustment:** This offset velocity is then added to the beam's direction, effectively pushing the beam away from the player's movement path.

### Laser Emission and Component Enabling

Once the direction and positioning are finalized, the script enables the laser.

*   **Component Access:** It retrieves all components of the laser entity.
*   **Enabling Emitter:** The `is_emitting` property of the first component (assumed to be the laser emitter) is set to `true`.
*   **Component Enable:** The laser emitter component and another component (likely for visual effects) are explicitly enabled.
*   **Tagging:** The `"enabled_in_world"` tag is added to ensure the laser remains active after the item is picked up.

### Cleanup

*   **Iris Sprite Removal:** If there's an additional child entity beyond the laser itself (likely the original iris sprite), it is killed to avoid duplicates or visual glitches.

```lua
-- Example of how the beam direction is calculated when moving fast:
local x,y = GameGetVelocityCompVelocity(entity_id)
if get_magnitude(x, y) <= 30 then
	-- align beam with item if moving slow/when in hand
	x,y = 1,0
	x,y = vec_rotate(x,y,rot)
else
	-- get angle from velocity
	x,y = vec_normalize(x,y)
	rot = math.atan2(y,x)
	rot_lerp_amount = 0.15
end

-- Example of player offset logic:
if IsPlayer(root_id) then
	local vx,vy = GameGetVelocityCompVelocity(root_id)
	local amount = math.max(vec_dot(vx,vy,x,y), 0) * 0.4
	amount = math.min(amount, 0.2)
	vx,vy = vec_mult(vx,vy, amount)
	x,y = vec_add(vx,vy,x,y)
end
```