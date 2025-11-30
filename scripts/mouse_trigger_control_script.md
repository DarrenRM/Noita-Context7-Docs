---
title: Mouse Trigger Control Script
category: scripts
---

# Mouse Trigger Control Script

This script defines a function `collision_trigger` that is intended to be used with entities that have the "controls_mouse" tag. When triggered, it iterates through all components of the closest entity with this tag and enables them.

## Key Functionality

### `collision_trigger()`

This function is the core of the script. It is designed to be called when a collision event occurs.

#### Logic:

1.  **Find Closest Entity:** It searches for the nearest entity that possesses the tag `"controls_mouse"`.
2.  **Retrieve Components:** It then retrieves all components associated with this found entity.
3.  **Enable Components:** If components are found, it iterates through each component and sets its enabled state to `true`.

#### Usage:

This function is typically attached to an entity's collision event handler. When another entity collides with the entity containing this script and the "controls_mouse" tag, `collision_trigger` will execute.

## Example Usage (Conceptual)

While the provided snippet is a function definition, its intended use would be within a larger entity definition. For instance, an entity might have a collision component that calls this function:

```lua
-- Conceptual example of how this script might be used
-- This is NOT part of the provided source, but illustrates its purpose.

-- Assume an entity has a collision component and this script is attached
-- EntityCreate(
--     -- ... other components
--     {
--         id = "collision_trigger_script",
--         script = "data/scripts/buildings/controls_mouse_trigger.lua",
--         callback = "collision_trigger" -- This would be the function to call on collision
--     }
-- )
```

## Important Notes

*   The script relies on the presence of an entity with the `"controls_mouse"` tag.
*   It assumes that enabling all components is the desired behavior for this trigger.
*   Error handling for cases where no entity with the tag is found is minimal (it simply returns).