---
title: Oil Receptacle Entity
category: entities
---

# Oil Receptacle Entity

This document describes the `receptacle_oil.xml` entity, which functions as a container for oil in Noita.

## Key Components

### MaterialAreaCheckerComponent

This component is responsible for detecting the presence of specific materials within a defined area.

*   **`area_aabb.min_x`**: `-4` (Minimum X-coordinate of the detection area)
*   **`area_aabb.max_x`**: `4` (Maximum X-coordinate of the detection area)
*   **`area_aabb.min_y`**: `-1` (Minimum Y-coordinate of the detection area)
*   **`area_aabb.max_y`**: `0` (Maximum Y-coordinate of the detection area)
*   **`update_every_x_frame`**: `1` (The checker updates its status every frame)
*   **`material`**: `oil` (The primary material to detect)
*   **`material2`**: `oil` (An additional material to detect, in this case, also oil)
*   **`look_for_failure`**: `0` (Does not trigger on material failure)
*   **`kill_after_message`**: `1` (The entity will be destroyed after a message is triggered)

### LuaComponent

This component links the entity to a Lua script for custom behavior.

*   **`script_material_area_checker_success`**: `data/scripts/buildings/receptacle_oil.lua` (The script executed when the `MaterialAreaCheckerComponent` successfully detects the specified materials)