---
title: Orb Mat Animate
category: guides
---

dofile( "data/scripts/lib/utilities.lua" )

function set_main_animation( current_name )
	local entity_id = GetUpdatedEntityID()
	edit_all_components( entity_id, "SpriteComponent", function(comp,vars)
		vars.rect_animation = current_name
	end)
end

set_main_animation( "detonate" )
```

---
title: Orb Mat Animate
category: entities
---

# Orb Mat Animate

This script is responsible for setting the main animation of an entity, specifically targeting the `SpriteComponent`.

## Core Functionality

The primary function `set_main_animation` takes a string argument `current_name` which represents the desired animation state. It then retrieves the `entity_id` of the currently updated entity and iterates through all its components. If a component is of type `SpriteComponent`, it modifies the `rect_animation` property to the provided `current_name`.

## Key Elements

*   **`set_main_animation( current_name )`**: The main function that orchestrates the animation change.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the entity being processed.
*   **`edit_all_components( entity_id, "SpriteComponent", function(comp,vars) ... end)`**: A utility function (likely from `utilities.lua`) that finds all components of a specific type (`SpriteComponent` in this case) on a given entity and applies a modification function to them.
*   **`vars.rect_animation = current_name`**: The crucial line that sets the animation state within the `SpriteComponent`.

## Usage Example

The script concludes with a direct call:

```lua
set_main_animation( "detonate" )
```

This line immediately sets the animation of the entity this script is attached to to "detonate". This suggests the entity is intended to perform a detonation animation upon its creation or activation.