---
title: Bomb Cart Projectile
category: scripts
---

---

# Bomb Cart Projectile

This script defines the behavior of the "Bomb Cart" projectile in Noita. It's designed to move along the ground and propel itself forward when near a surface.

## Key Attributes and Behavior

### Movement Logic

*   **Ground Proximity Detection:** The cart only propels itself forward when it detects a platform within a certain range below it (using `RaytracePlatforms`).
*   **Direction Control:**
    *   A `reverse` variable (likely controlled by an external component) determines the direction of movement.
    *   If `reverse` is true, the cart moves backward (`-1`); otherwise, it moves forward (`1`).
*   **Speed:** The base speed is `15`, which is then multiplied by the determined direction.

### Physics Application

*   **Motor Speed:** The calculated `speed` is applied to any `PhysicsJoint2MutatorComponent` attached to the entity, controlling its rotational movement.
*   **Force Application:**
    *   A small forward force (`speed * 0.25`) is applied for smoother movement.
    *   Additional gravity (`5`) is applied to increase traction with the ground.

## Lua Script Snippet

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local speed = 15
local dir = 0

-- propel forward only when close to ground
if RaytracePlatforms(x,y+15,x,y+35) then	
	local is_reversed = ComponentGetValue2(get_variable_storage_component(entity_id, "reverse"), "value_bool")
	dir = is_reversed and -1 or 1
end
speed = speed * dir

-- apply speed to motors
for _,comp in pairs(EntityGetComponent(entity_id, "PhysicsJoint2MutatorComponent")) do
	component_write( comp, { motor_speed = speed })
end

-- extra gravity for traction + some direct force for smoother movement
PhysicsApplyForce(entity_id, speed * 0.25, 5)
```