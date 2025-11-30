---
title: Physics Joint Mouse Joint Stopper
category: scripts
---

# Physics Joint Mouse Joint Stopper

This script provides a function to stop or reset the movement of entities connected by a mouse joint in Noita.

## Function: `stop_mouse_joint()`

This function is designed to be called to immediately halt any motion associated with a mouse joint component attached to an entity.

### Core Logic

1.  **Get Updated Entity ID**: It first retrieves the `entity_id` of the entity that is currently being updated. This ensures the script operates on the correct entity.
2.  **Edit Physics Joint Component**: It then iterates through all components of the specified entity.
3.  **Target `PhysicsJointComponent`**: The script specifically targets components of type `PhysicsJointComponent`.
4.  **Reset Delta Values**: For each `PhysicsJointComponent` found, it resets the `delta_x` and `delta_y` values to `0`. These values typically represent the displacement or velocity components of the joint, and setting them to zero effectively stops the joint's movement.

### Usage

The `stop_mouse_joint()` function is called directly at the end of the script, indicating it's intended to be executed once when the script is loaded or triggered.

```lua
dofile_once("data/scripts/lib/utilities.lua")

function stop_mouse_joint()
	print( "stop_mouse_joint") -- Debugging output
	local entity_id = GetUpdatedEntityID()

	edit_all_components( entity_id, "PhysicsJointComponent", function(comp,vars)
		vars.delta_x = 0
		vars.delta_y = 0
	end)
end

stop_mouse_joint()
```