---
title: Null Room Check 1 Entity
category: entities
---

# Null Room Check 1 Entity

This entity defines a component within the Noita game world, specifically related to the "Null Room" mechanic. It's designed to check for specific material conditions within a defined area and trigger a Lua script upon success.

## Key Components

### UIInfoComponent
This component provides basic information for the entity, primarily its name as displayed in the game.

*   **name**: `$building_altar_null` - The internal identifier for this building/entity.

### LightComponent
This component adds a light source to the entity, making it visible and potentially interactive in the game world.

*   **_tags**: `enabled_in_world,enabled_in_hand` - Indicates the light is active when the entity is in the world or held.
*   **radius**: `96` - The radius of the light's influence.
*   **r, g, b**: `255, 255, 255` - Sets the light color to white.
*   **fade_out_time**: `0.2` - The time it takes for the light to fade out.

### MaterialAreaCheckerComponent
This is the core component responsible for detecting specific materials within a defined spatial area.

*   **area\_aabb.min\_x, area\_aabb.min\_y, area\_aabb.max\_x, area\_aabb.max\_y**: Defines a bounding box for the area check.
    *   `min_x`: `4`
    *   `min_y`: `-3`
    *   `max_x`: `6`
    *   `max_y`: `3`
*   **material**: `blood` - The primary material to look for.
*   **material2**: `blood` - A secondary material to look for (in this case, the same as the primary).
*   **kill\_after\_message**: `0` - Prevents the entity from being destroyed after a message is triggered.
*   **look\_for\_failure**: `0` - Does not trigger an action if the material check fails.

### LuaComponent
This component links the entity's behavior to a specific Lua script, executed when the `MaterialAreaCheckerComponent`'s conditions are met.

*   **script\_material\_area\_checker\_success**: `data/scripts/magic/null_room/check1_success.lua` - The path to the Lua script that runs when the material check is successful.