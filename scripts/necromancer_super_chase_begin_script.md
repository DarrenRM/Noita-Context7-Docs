---
title: Necromancer Super Chase Begin Script
category: scripts
---

# Necromancer Super Chase Begin Script

This script controls the initial phase of a Necromancer's "super chase" behavior in Noita. It determines when the Necromancer should begin actively pursuing the player based on proximity and line of sight.

## Key Functionality

The primary goal of this script is to trigger the Necromancer's chase state. This is achieved by:

1.  **Proximity Check:** Evaluating the distance between the Necromancer and the player.
2.  **Line of Sight (LOS) Check:** Verifying if there are any surfaces obstructing the view between the Necromancer and the player.
3.  **State Transition:** If the conditions are met (player is within range and LOS is clear), the script enables chase components and removes itself.

## Configuration Attributes

The behavior of this script is influenced by a few key variables:

*   `max_range`: The maximum distance (in pixels) at which the Necromancer will consider initiating a chase.
*   `min_range`: The minimum distance (in pixels) at which the Necromancer will immediately initiate a chase, bypassing LOS checks.

## Core Logic Breakdown

The script performs the following steps:

1.  **Initialization:**
    *   Retrieves the Necromancer's entity ID and current position.
2.  **Target Acquisition:**
    *   Finds the closest entity with the tag `"player_unit"`.
    *   If no player is found, the script terminates.
3.  **Distance Calculation:**
    *   Gets the player's position and calculates the distance between the Necromancer and the player.
4.  **Range Checks:**
    *   **Too Far:** If the distance exceeds `max_range`, the script terminates.
    *   **Very Near:** If the distance is less than `min_range`, the `start_chase()` function is called immediately.
5.  **Line of Sight (LOS) Check:**
    *   If the player is within `max_range` but not within `min_range`, a raytrace is performed from the Necromancer to the player.
    *   If the raytrace does *not* hit any surfaces (`not did_hit`), the `start_chase()` function is called.

## `start_chase()` Function

This internal function is responsible for transitioning the Necromancer into its active chase state:

*   **Enables Chase Components:** It activates components tagged with `"enable_when_player_seen"`.
*   **Removes Script:** It removes the current script component from the Necromancer entity, preventing it from running again.

```lua
local max_range = 150
local min_range = 50

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform(entity_id)

local function start_chase()
	-- enable chase & cell eater, disable this script
	print("start chase")
	EntitySetComponentsWithTagEnabled(entity_id, "enable_when_player_seen", true)
	EntityRemoveComponent(entity_id, GetUpdatedComponentID())
end

local target = EntityGetClosestWithTag(pos_x, pos_y, "player_unit")
if not target or target == 0 then return end

local tx, ty = EntityGetTransform(target)
local dist = get_distance(tx, ty, pos_x, pos_y)
if dist > max_range then return end -- too far
if dist < min_range then
	-- very near
	start_chase()
	return
end

-- check los
local did_hit = RaytraceSurfaces(pos_x, pos_y, tx, ty)
if not did_hit then start_chase() end
```