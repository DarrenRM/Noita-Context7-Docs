---
title: Dark Ghost AI Behavior
category: scripts
---

---

# Dark Ghost AI Behavior

This script defines a simple AI behavior for the "Dark Ghost" entity in Noita. It primarily focuses on a randomized visual effect.

## Key Attributes

### Visual Animation Trigger

*   **Random Chance:** The script introduces a random chance (`rand == 2`) to trigger a visual animation change. This means the effect doesn't happen every frame or every time the entity spawns.
*   **Animation Swap:** When triggered, the entity's sprite component is modified to play the "blink" animation and then transition to the "stand" animation.

### Script Logic

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()

-- Sets a random seed based on the entity's ID and the current game frame.
-- This ensures the randomness is consistent for a specific entity instance
-- within a given game state, but varies across different spawns.
SetRandomSeed( entity_id, GameGetFrameNum() )

-- Generates a random integer between 1 and 10.
local rand = Random(1,10)

-- Checks if the random number is 2. This gives a 1 in 10 chance for the following code to execute.
if (rand == 2) then
	-- Edits all components of type "SpriteComponent" attached to the entity.
	edit_all_components( entity_id, "SpriteComponent", function(comp,vars)
		-- Sets the current animation to "blink".
		ComponentSetValue( comp, "rect_animation",      "blink" )
		-- Sets the animation to transition to after "blink" finishes to "stand".
		ComponentSetValue( comp, "next_rect_animation", "stand" )
	end)
end
```