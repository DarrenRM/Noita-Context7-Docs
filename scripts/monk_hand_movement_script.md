---
title: Monk Hand Movement Script
category: scripts
---

# Monk Hand Movement Script

This script controls the movement and visual behavior of the "monk hand" entities in Noita. It's designed to make the hands appear to float, bob, and rotate independently while maintaining a connection to their parent entity (likely the monk's body).

## Key Functionality

### Movement and Positioning

*   **Target Following:** The hand entity continuously interpolates (lerps) towards a target position. This target position is derived from the parent entity's transform, with an offset to create separation.
*   **Bobbing Motion:** The target position is further modified by a sine wave function, creating a vertical and horizontal bobbing effect. This gives the impression of the hand floating or gently moving.
*   **Handedness Offset:** The script reads a variable (`is_right`) to determine if the hand is a right or left hand. This adjusts the horizontal offset (`offset_x`) accordingly, ensuring the hands are positioned correctly relative to the parent.

### Rotation

*   **Dynamic Rotation:** The hand entity rotates based on a sine wave function applied to the game time. This results in a subtle, oscillating rotation.
*   **Randomized Speeds:** To prevent multiple hands from moving in perfect sync, the script introduces slight randomization to the bobbing speeds and rotation speed based on the entity's ID.

### Arm Particle FX

*   **Arm Visuals:** The script manages the positioning of child entities tagged as "arm\_fx". These are likely particle effects or sprites that visually represent the arms connecting the hand to the body.
*   **Interpolated Positioning:** The arm FX are positioned along the vector between the parent entity's "shoulder" position and the hand's current position. The exact point is determined by a procedural random value.
*   **Distortion:** The arm FX positions are further distorted using sine waves, creating a wobbling or dynamic effect that complements the hand's movement.

## Key Attributes and Variables

| Attribute         | Description                                                                                                |
| :---------------- | :--------------------------------------------------------------------------------------------------------- |
| `lerp_amount`     | Controls how quickly the hand interpolates towards its target position. Higher values mean faster movement. |
| `offset_x`        | The horizontal distance of the hand from its parent. Adjusted for handedness.                              |
| `bob_h`           | The maximum height of the vertical bobbing motion.                                                         |
| `bob_w`           | The maximum width of the horizontal bobbing motion.                                                        |
| `bob_speed_y`     | Controls the speed of the vertical bobbing motion.                                                         |
| `bob_speed_x`     | Controls the speed of the horizontal bobbing motion.                                                       |
| `rotate_amount`   | The maximum angle of rotation.                                                                             |
| `rotate_speed`    | Controls the speed of the rotation.                                                                        |
| `is_right`        | A boolean variable indicating if the hand is the right hand. Determines `offset_x`.                        |
| `arm_fx` tag      | A tag applied to child entities that represent the arm particle effects.                                   |

## Code Structure

The script primarily consists of:

1.  **Initialization:** Setting up movement parameters and retrieving the entity's ID and initial transform.
2.  **Target Calculation:** Determining the floating target position based on the parent's transform and offsets.
3.  **Randomization:** Applying slight variations to movement speeds and lerp amount for visual diversity.
4.  **Movement and Rotation Update:** Calculating and applying the new position and rotation to the hand entity.
5.  **Arm FX Management:** Iterating through child entities to update the position of arm particle effects.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local lerp_amount = 0.9
local offset_x = 15
local bob_h = 8
local bob_w = 20
local bob_speed_y = 0.023
local bob_speed_x = 0.01121
local rotate_amount = math.pi * 0.05
local rotate_speed = 0.093

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

if pos_x == 0 and pos_y == 0 then
	pos_x, pos_y = EntityGetTransform(EntityGetParent(entity_id))
end


-- ghost continously lerps towards a target that floats around the parent
local target_x, target_y = EntityGetTransform(EntityGetParent(entity_id))
local body_x, body_y = target_x, target_y -- store for drawing the arms
if target_x == nil then return end
target_y = target_y - 20

-- handedness from variable storage
local comp = get_variable_storage_component(entity_id, "is_right")
is_right = ComponentGetValue2(comp, "value_bool")
if not is_right then offset_x = -offset_x end

target_x = target_x + offset_x

local time = GameGetFrameNum()
local r = ProceduralRandomf(entity_id, 0, -1, 1)

-- randomize times and speeds slightly so that multiple fists don't fly identically
time = time + r * 10000
bob_speed_y = bob_speed_y + (r * bob_speed_y * 0.1)
bob_speed_x = bob_speed_x + (r * bob_speed_x * 0.1)
lerp_amount = lerp_amount - (r * lerp_amount * 0.01)

-- bob
target_y = target_y + math.sin(time * bob_speed_y) * bob_h
target_x = target_x + math.sin(time * bob_speed_x) * bob_w

-- rotate
rotate_amount = rotate_amount * math.sin(time * rotate_speed)

-- move towards target
pos_x,pos_y = vec_lerp(pos_x, pos_y, target_x, target_y, lerp_amount)
EntitySetTransform( entity_id, pos_x, pos_y, rotate_amount, 1, 1)

-- "arms" particle fx position.
-- sets the fx entity position to between hand and body and wobbles it!
do
	local children = EntityGetAllChildren(entity_id)
	if children == nil or #children == 0 then return end

	local x = pos_x
	local y = pos_y
	
	-- "shoulder" position
	body_y = body_y - 10
	offset_x = 4
	if not is_right then offset_x = -offset_x end
	body_x = body_x + offset_x

	for _,fx_entity in pairs(children) do
		if EntityHasTag(fx_entity, "arm_fx") then

			-- pick a position between body and hand. 0 is body, 1 is hand
			local pos = ProceduralRandomf(time, fx_entity)

			-- figure out how much to distort the position
			-- middle distorts most so we want a range of 0 to 1 to 0
			local amount = pos * 2 - 1 -- 0...1 -> -1...0...1
			amount = -math.abs(amount) -- -1...0...-1
			amount = amount + 1 -- 0...1...0

			local distort_x = math.sin((x + time) * 0.03) * 8 * amount
			local distort_y = math.sin((y + time) * 0.05734 + 40) * 4 * amount

			x, y = vec_lerp(body_x, body_y, x, y, pos)
			x = x + distort_x
			y = y + distort_y
			--GameCreateParticle("spark_red_bright", x, y, 1, 0, 0, true)
			EntitySetTransform(fx_entity, x, y)
		end
	end
end
```