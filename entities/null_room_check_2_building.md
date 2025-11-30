---
title: Null Room Check 2 Building
category: entities
---

# Null Room Check 2 Building

This entity represents a component within the "Null Room" system, specifically designed to check for the presence of certain materials.

## Key Components

### LuaComponent
This component executes a Lua script periodically to perform checks.

*   **`execute_every_n_frame`**: `20` - The script will run every 20 frames.
*   **`script_source_file`**: `data/scripts/magic/null_room/check.lua` - The main Lua script responsible for the logic.

### UIInfoComponent
Provides information for the user interface.

*   **`name`**: `$building_altar_null` - The internal name used for UI elements.

### LightComponent
Adds a light source to the entity.

*   **`radius`**: `96` - The radius of the light.
*   **`r`, `g`, `b`**: `255`, `255`, `255` - White light color.
*   **`fade_out_time`**: `0.2` - How quickly the light fades.

### MaterialAreaCheckerComponent
This component checks a specific area for certain materials.

*   **`area_aabb.min_x`**: `4`
*   **`area_aabb.min_y`**: `-3`
*   **`area_aabb.max_x`**: `6`
*   **`area_aabb.max_y`**: `3` - Defines a small rectangular area for the check.
*   **`material`**: `alcohol` - The primary material to look for.
*   **`material2`**: `alcohol` - A secondary material to look for (in this case, the same).
*   **`kill_after_message`**: `0` - Does not kill the entity after a message.
*   **`look_for_failure`**: `0` - Does not specifically look for a failure condition.

### LuaComponent (Success Handler)
This component defines what happens when the `MaterialAreaCheckerComponent` succeeds.

*   **`script_material_area_checker_success`**: `data/scripts/magic/null_room/check1_success.lua` - The Lua script executed upon successful material detection.