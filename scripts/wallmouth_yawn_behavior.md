---
title: Wallmouth Yawn Behavior
category: scripts
---

---

# Wallmouth Yawn Behavior

This script defines the behavior for a "wallmouth" entity, specifically its occasional "yawn" animation.

## Core Functionality

The script primarily focuses on:

*   **Randomized Yawning:** The wallmouth has a chance to perform a "yawn" animation based on a random number generated each frame.
*   **Animation Triggering:** If the random condition is met, it attempts to play a specific animation named "yawn".

## Key Attributes & Elements

*   **`entity_id`**: Retrieves the unique identifier for the wallmouth entity.
*   **`pos_x`, `pos_y`**: Gets the current position of the entity.
*   **`SetRandomSeed`**: Initializes the random number generator using the entity's position and frame number for varied outcomes.
*   **`Random(0, 10)`**: Generates a random integer between 0 and 10 (inclusive).
*   **`edit_component` (VelocityComponent, CharacterDataComponent)**: These calls ensure that the entity's velocity is reset to (0, 0) each frame, preventing unintended movement.
*   **`if ( rnd == 5 )`**: The condition that triggers the yawn animation. This means there's a 1 in 11 chance (0-10) for the yawn to occur.
*   **`EntityGetFirstComponent( entity_id, "SpriteComponent" )`**: Checks if the entity has a `SpriteComponent`, which is necessary for playing animations.
*   **`GamePlayAnimation( entity_id, "yawn", 0, "stand", 0 )`**: Plays the "yawn" animation.
    *   `"yawn"`: The name of the animation to play.
    *   `0`: The starting frame of the animation.
    *   `"stand"`: The animation state to transition to after "yawn" finishes.
    *   `0`: The starting frame of the "stand" state.

## Example Usage (Conceptual)

This script would be attached to an entity that visually resembles a wall with a mouth. When this entity is active in the game, it will periodically perform a "yawn" animation, adding a subtle visual detail.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Seed the random number generator for varied outcomes
SetRandomSeed( pos_x + GameGetFrameNum(), pos_y - 32523 )

local rnd = Random( 0, 10 ) -- Generate a random number between 0 and 10

-- Ensure the entity has no velocity
edit_component( entity_id, "VelocityComponent", function(comp,vars)
	ComponentSetValueVector2( comp, "mVelocity", 0, 0 )
end)

edit_component( entity_id, "CharacterDataComponent", function(comp,vars)
	ComponentSetValueVector2( comp, "mVelocity", 0, 0 )
end)

-- Check if the random condition is met to trigger a yawn
if ( rnd == 5 ) then
	local sprite = EntityGetFirstComponent( entity_id, "SpriteComponent" )
	if ( sprite ~= nil ) then
		-- Play the "yawn" animation
		GamePlayAnimation( entity_id, "yawn", 0, "stand", 0 )
	end
end
```