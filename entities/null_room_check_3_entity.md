---
title: Null Room Check 3 Entity
category: entities
---

# Null Room Check 3 Entity

This entity defines a component of the "Null Room" in Noita, specifically a check that interacts with the environment.

## Key Components

### UIInfoComponent
This component provides basic information for the UI, such as the name displayed for this entity.

*   **name**: `$building_altar_null` (Internal identifier for the Null Room altar)

### LightComponent
This component adds a light source to the entity.

*   **_tags**: `enabled_in_world`, `enabled_in_hand` (Indicates when the light is active)
*   **radius**: `96` (The radius of the light effect)
*   **r**, **g**, **b**: `255`, `255`, `255` (White light color)
*   **fade_out_time**: `0.2` (How quickly the light fades)

### MaterialAreaCheckerComponent
This is the core component for this entity, responsible for checking a specific area for materials.

*   **area\_aabb.min\_x**: `4`
*   **area\_aabb.min\_y**: `-3`
*   **area\_aabb.max\_x**: `6`
*   **area\_aabb.max\_y**: `3`
    *   These define a small rectangular area relative to the entity's position.
*   **material**: `silver`
*   **material2**: `silver`
    *   The checker looks for the presence of "silver" material within the defined area.
*   **kill\_after\_message**: `0` (Does not kill the entity after a message)
*   **look\_for\_failure**: `0` (Does not specifically look for a failure condition)

### LuaComponent
This component links the `MaterialAreaCheckerComponent` to a Lua script that executes upon success.

*   **script\_material\_area\_checker\_success**: `data/scripts/magic/null_room/check1_success.lua`
    *   This script is executed when the `MaterialAreaCheckerComponent` successfully finds the specified materials.