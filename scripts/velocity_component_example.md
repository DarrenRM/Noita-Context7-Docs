---
title: Velocity Component Example
category: scripts/
---

# Velocity Component Example

This script demonstrates how to access and print the velocity of an entity using the `VelocityComponent`.

## Key Functionality

*   **GetUpdatedEntityID()**: Retrieves the unique identifier for the currently processed entity.
*   **EntityGetComponent(entity_id, "VelocityComponent")**: Fetches all components of type "VelocityComponent" attached to the specified entity.
*   **ComponentGetValueVector2(component_id, "mVelocity")**: Retrieves the 2D vector value of the "mVelocity" property from a given component.

## Lua Script

```lua
local entity_id = GetUpdatedEntityID()

local comp_ids = EntityGetComponent( entity_id, "VelocityComponent" )
if( comp_ids ~= nil ) then
	local x,y = ComponentGetValueVector2( comp_ids[1], "mVelocity")
	print( x, y )
end
```

## Explanation

1.  The script first obtains the `entity_id` of the current entity.
2.  It then attempts to find any `VelocityComponent` attached to this entity.
3.  If a `VelocityComponent` is found, it retrieves the `mVelocity` property, which is a 2D vector representing the entity's speed and direction.
4.  Finally, it prints the X and Y components of the velocity to the console.

This is a foundational example for understanding how to interact with physics-related components in Noita mods.