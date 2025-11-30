---
title: Teleport Hourglass Return Logic
category: scripts
---

# Teleport Hourglass Return Logic

This script defines the visual effects and teleportation behavior for the "Teleport Hourglass Return" entity in Noita. It manages the rotation and pulsing of associated visual effect (FX) entities and sets the return destination for the TeleportComponent.

## Key Functionality

### Visual Effects Management

The script animates child entities tagged as "fx" to create a swirling, pulsing visual effect around the hourglass.

*   **Rotation:** Child entities rotate around the hourglass's origin. The rotation speed is influenced by a base rotation and two sine wave functions, creating a dynamic, non-uniform spin.
    *   `rot_speed`: Base rotation speed.
    *   `twist_speed_1`, `twist_amount_1`: Parameters for the first sine wave twist.
    *   `twist_speed_2`, `twist_amount_2`: Parameters for the second sine wave twist.
*   **Pulsing Radius:** The radius of the FX entities' visual effect (controlled by `ParticleEmitterComponent.offset`) pulses over time, creating a breathing or expanding/contracting visual.
    *   `circle_scale_min`, `circle_scale_max`: Define the minimum and maximum range for the pulsing radius.
    *   `pulse_speed`: Controls the speed of the pulsing effect.

### Teleportation Target Setting

Periodically, the script updates the `TeleportComponent`'s target coordinates. This ensures the hourglass always teleports the player back to a specific, procedurally determined location.

*   **Target Update Frequency:** The target is updated every 71 frames (`time % 71 == 0`).
*   **Return Locations:** The script defines two potential return locations:
    *   `teleport_back_x = -2210`, `teleport_back_y = 5223` (default)
    *   `teleport_back_x = 1707` (if `ProceduralRandom(0,0) > 0.5`)
*   **Seed Matching:** A crucial note indicates that the procedural generation for the return location must match the seed used in `snowcastle_cavern.lua`'s `init()` function.

## Key Attributes & Variables

| Attribute/Variable      | Description                                                                                             |
| :---------------------- | :------------------------------------------------------------------------------------------------------ |
| `entity_id`             | The unique identifier for the current entity.                                                           |
| `pos_x`, `pos_y`        | The current X and Y coordinates of the entity.                                                          |
| `time`                  | The current frame number in the game.                                                                   |
| `rot_speed`             | Base speed for the rotation of FX entities.                                                             |
| `twist_speed_1`         | Speed parameter for the first sine wave used in rotation.                                               |
| `twist_amount_1`        | Amplitude parameter for the first sine wave used in rotation.                                           |
| `twist_speed_2`         | Speed parameter for the second sine wave used in rotation.                                              |
| `twist_amount_2`        | Amplitude parameter for the second sine wave used in rotation.                                          |
| `circle_scale_min`      | Minimum radius for the pulsing FX effect.                                                               |
| `circle_scale_max`      | Maximum radius for the pulsing FX effect.                                                               |
| `pulse_speed`           | Speed at which the FX radius pulses.                                                                    |
| `children`              | A table containing all child entities of the hourglass.                                                 |
| `fx_entity`             | An individual child entity that is part of the visual effect.                                           |
| `ParticleEmitterComponent` | Component responsible for particle effects, used here to control the pulsing radius.                    |
| `TeleportComponent`     | Component responsible for teleportation, used here to set the return target.                            |
| `teleport_back_x`, `teleport_back_y` | Coordinates for the teleportation return destination.                                                 |

## Code Structure

The script follows a standard Lua structure:

1.  **Initialization:** Loads utilities, gets entity ID and transform, and initializes time.
2.  **Variable Declaration:** Defines parameters for rotation and pulsing effects.
3.  **Child Entity Processing:** Iterates through child entities to apply visual effects.
    *   Checks if a child entity has the "fx" tag.
    *   Calculates and sets the entity's transform (rotation).
    *   Finds the `ParticleEmitterComponent` and updates its `offset` for pulsing.
4.  **Teleport Target Update:** Periodically checks and updates the `TeleportComponent`'s target coordinates.
5.  **Debug/Commented Code:** Includes commented-out lines for potential debugging.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )
local time = GameGetFrameNum()

local rot_speed = 0.003
local twist_speed_1 = 0.02
local twist_amount_1 = 0.6
local twist_speed_2 = 0.012217
local twist_amount_2 = 0.7
local circle_scale_min = -120
local circle_scale_max = 2
local pulse_speed = 0.004

local children = EntityGetAllChildren(entity_id)
if children == nil or #children == 0 then return end

-- rotation along circle + twists
local rot = time * rot_speed
rot = rot + math.sin(time * twist_speed_1) * twist_amount_1 + math.sin(time * twist_speed_2) * twist_amount_2

-- set the fx entity positions
for i,fx_entity in pairs(children) do
	if EntityHasTag(fx_entity, "fx") then
		-- set entity rotation (entities stay in same position)
		local circle_pos = math.pi * 2 / #children * i
		circle_pos = circle_pos + rot
		EntitySetTransform(fx_entity, pos_x, pos_y, rot + circle_pos)

		-- change radius via particle offset
		local comp = EntityGetFirstComponent( fx_entity, "ParticleEmitterComponent")
		if comp ~= nil then
			circle_pos = (math.sin(time * pulse_speed) + 1) * 0.5
			ComponentSetValue2(comp, "offset", 0, lerp(circle_scale_max, circle_scale_min, circle_pos))
		end
	end
end

-- set teleport return target to match origin
if time % 71 == 0 then
	local teleport_comp = EntityGetFirstComponentIncludingDisabled( entity_id, "TeleportComponent" )

	if( teleport_comp ~= nil ) then
		local teleport_back_x = -2210
		local teleport_back_y = 5223

		-- NOTE: make sure seed matches with snowcastle_cavern.lua init()!
		if ProceduralRandom(0,0) > 0.5 then teleport_back_x = 1707 end

		ComponentSetValue2( teleport_comp, "target", teleport_back_x, teleport_back_y )
	end
end

-- hide teleporter for debug
--EntitySetComponentsWithTagEnabled(GetUpdatedEntityID(), "enabled_by_liquid", false)
```