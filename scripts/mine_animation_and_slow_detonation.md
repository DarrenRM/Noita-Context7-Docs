---
title: Mine Animation and Slow Detonation
category: scripts
---

---

# Mine Animation and Slow Detonation

This script modifies the behavior of a "mine" projectile in Noita, specifically its animation and detonation timer.

## Key Functionality

### Animation Change
The script sets the main animation of the entity to `"detonate"`. This likely triggers a visual effect associated with the mine's explosion.

### Detonation Timer Modification
The `CollisionTriggerComponent`'s `timer_for_destruction` is multiplied by 5. This significantly slows down the time it takes for the mine to detonate after its collision trigger is activated.

## Code Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

-- Function to set the main animation of an entity
function set_main_animation( current_name )
	local entity_id = GetUpdatedEntityID()
	edit_all_components( entity_id, "SpriteComponent", function(comp,vars)
		vars.rect_animation = current_name -- Sets the animation name
	end)
end

-- Apply the "detonate" animation
set_main_animation( "detonate" )

-- Get the entity ID
local entity_id = GetUpdatedEntityID()

-- Modify the CollisionTriggerComponent
edit_component( entity_id, "CollisionTriggerComponent", function(comp,vars)
	local timer = ComponentGetValueInt( comp, "timer_for_destruction")
	vars.mTimer = timer * 5 -- Slows down the detonation timer
end)
```

## Relevant Components

*   **SpriteComponent**: Responsible for visual aspects, including animations.
*   **CollisionTriggerComponent**: Handles collision detection and triggers subsequent actions, such as detonation.
    *   `timer_for_destruction`: The original time in frames before destruction.
    *   `mTimer`: The modified timer value, used here to extend the detonation delay.