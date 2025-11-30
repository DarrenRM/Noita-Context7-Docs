---
title: Projectile Repulsion Perk
category: scripts
---

# Projectile Repulsion Perk

This script implements the "Projectile Repulsion" perk in Noita. When acquired, it causes projectiles within a certain radius to be pushed away from the player.

## Core Functionality

The perk's primary function is to detect and modify the velocity of nearby projectiles.

### Key Attributes and Behaviors

*   **Detection Radius:** `distance_full` defines the maximum distance from the player at which projectiles will be affected.
*   **Repulsion Strength:** The strength of the repulsion is influenced by `gravity_coeff`, which is scaled by the number of times the perk has been picked up (`pickup_count`).
*   **Directional Influence:** A random directional offset (`direction_random`) is applied to the repulsion, making the push less predictable.
*   **Proximity Scaling:** The repulsion force is stronger for projectiles closer to the player, determined by `gravity_percent`.
*   **Resistance Tag:** Projectiles with the tag "resist\_repulsion" have their repulsion strength significantly reduced.

## Technical Implementation

The script utilizes several Noita API functions to achieve its effect.

### Important Functions and Logic

*   `EntityGetInRadiusWithTag`: Used to find all entities tagged as "projectile" within the specified radius.
*   `EntityGetTransform`: Retrieves the position of the player and nearby projectiles.
*   `get_distance` and `get_direction`: Helper functions to calculate the distance and angle between the player and a projectile.
*   `EntityGetComponent` and `edit_component`: Used to access and modify the `VelocityComponent` of projectiles.
*   `ComponentGetValueVector2` and `ComponentSetValueVector2`: Functions to read and write the velocity vector of a projectile.
*   `math.cos`, `math.sin`, `math.rad`, `Random`: Standard Lua math functions for calculating directional offsets.
*   `get_stored_perk_pickup_count`: Retrieves how many times this specific perk has been picked up by the player, influencing its power.

### Example Logic Snippet

```lua
-- Calculate the repulsion force based on distance and pickup count
local gravity_percent = math.max(( distance_full - distance ) / distance_full, 0.01)
local gravity_coeff = 96 * pickup_count
if EntityHasTag(projectile_id, "resist_repulsion") then gravity_coeff = gravity_coeff * 0.25 end

-- Apply the calculated offset to the projectile's velocity
edit_component( projectile_id, "VelocityComponent", function(comp,vars)
    local vel_x,vel_y = ComponentGetValueVector2( comp, "mVelocity")
    
    local offset_x = math.cos( direction + direction_random ) * ( gravity_coeff * gravity_percent )
    local offset_y = 0 - math.sin( direction + direction_random ) * ( gravity_coeff * gravity_percent )

    vel_x = vel_x + offset_x
    vel_y = vel_y + offset_y

    ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y)
end)
```