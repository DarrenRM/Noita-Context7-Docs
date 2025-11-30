---
title: Bomb Cart Projectile Initialization
category: scripts/
---

# Bomb Cart Projectile Initialization

This script initializes the `bomb_cart` projectile, setting its initial trajectory and direction. It's designed to propel the projectile away from its shooter.

## Key Attributes

*   **`force_x`**: The initial horizontal force applied to the projectile.
*   **`force_y`**: The initial vertical force applied to the projectile.
*   **`dir`**: Determines the horizontal direction of the projectile, calculated based on the relative position of the shooter.
*   **`is_reversed`**: A boolean flag stored to indicate if the projectile's direction is reversed (i.e., moving left). This is used by `bomb_cart.lua` for further logic.

## Initialization Logic

1.  **Get Entity ID and Transform**: Retrieves the unique ID and position of the projectile entity.
2.  **Determine Direction**:
    *   It finds the `ProjectileComponent` to identify the entity that shot this projectile (`mWhoShot`).
    *   If the shooter is identified, it calculates the horizontal direction (`dir`) by comparing the projectile's X-coordinate with the shooter's X-coordinate. A positive `dir` means the projectile moves right, and a negative `dir` means it moves left.
3.  **Apply Force**:
    *   The `force_x` is multiplied by the calculated `dir` to ensure the projectile is propelled away from the shooter horizontally.
    *   `PhysicsApplyForce` is used to give the projectile its initial velocity.
4.  **Store Direction State**: The `is_reversed` state is stored in the entity's variable storage for use by the projectile's main behavior script (`bomb_cart.lua`).

```lua
--[[
    Initializes the bomb_cart projectile.
    Propels it away from the shooter.
]]

dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform( entity_id )

local force_x = 600
local force_y = -200
local dir = 0

-- propel away from shooter
local comp = EntityGetFirstComponent( entity_id, "ProjectileComponent" )
if comp == nil then return end
local who_shot = ComponentGetValue2( comp, "mWhoShot")
if( who_shot == nil or who_shot == 0 ) then return end

dir = sign(x - EntityGetTransform(who_shot))

-- store initial direction for bomb_cart.lua
local is_reversed = ComponentSetValue2(get_variable_storage_component(entity_id, "reverse"), "value_bool", dir < 0)

force_x = force_x * dir

PhysicsApplyForce(entity_id, force_x, force_y)
```