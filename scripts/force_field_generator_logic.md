---
title: Force Field Generator Logic
category: scripts
---

# Force Field Generator Logic

This script controls the behavior of a force field generator entity in Noita. It dynamically enables or disables visual components and child entities based on the proximity of enemies or the player.

## Core Functionality

The primary goal of this script is to activate the force field's visual elements and associated shield components when a target (enemy or player) is within a specified range.

## Key Attributes and Logic

### `distance_threshold`
- **Type:** `number`
- **Description:** Defines the maximum distance (in pixels) from the generator at which the force field will remain active. If the closest target is further away than this threshold, the force field will deactivate.
- **Default Value:** `38`

### Proximity Detection
The script performs the following checks to determine if the force field should be active:
1.  **Find Closest Enemy:** Uses `EntityGetClosestWithTag(x, y, "enemy")` to locate the nearest entity with the "enemy" tag.
2.  **Find Closest Player:** Uses `EntityGetClosestWithTag(x, y, "player_unit")` to locate the nearest entity with the "player_unit" tag.
3.  **Calculate Minimum Distance:** It calculates the distance to both the closest enemy and the player (if they exist) and stores the smallest of these distances in the `dist` variable.

### Activation Condition
- **Logic:** `local enable = dist > distance_threshold`
- **Description:** A boolean variable `enable` is set to `true` if the closest detected target is *further* than the `distance_threshold`. This means the force field *deactivates* when targets are close and *activates* when they are far.

## Component Management

### Visual Component (`SpriteComponent`)
- **Logic:** `edit_all_components( entity_id, "SpriteComponent", function(comp,vars) ... end)`
- **Description:** This section iterates through all `SpriteComponent`s attached to the generator entity.
    - If `enable` is `true` (target is far), the sprite's `visible` property is set to `1` (visible).
    - If `enable` is `false` (target is near), the sprite's `visible` property is set to `0` (hidden).
    - *Note: The commented-out lines suggest an alternative method of enabling/disabling sprites directly.*

### Child Entity Components (`shield_entity`)
- **Logic:**
    ```lua
    local children = EntityGetAllChildren( entity_id)
    if children == nil then return end

    for _,v in ipairs(children) do
        if EntityGetTags(v) == "shield_entity" then
            EntitySetComponentsWithTagEnabled( v, "enabled_while_shielding", enable )
        end
    end
    ```
- **Description:**
    1.  The script retrieves all child entities of the generator using `EntityGetAllChildren`.
    2.  It then iterates through these children.
    3.  If a child entity has the tag `"shield_entity"`, its components tagged with `"enabled_while_shielding"` are enabled or disabled based on the `enable` variable.
        - When `enable` is `true` (targets are far), components tagged `"enabled_while_shielding"` on child entities are enabled.
        - When `enable` is `false` (targets are near), components tagged `"enabled_while_shielding"` on child entities are disabled.