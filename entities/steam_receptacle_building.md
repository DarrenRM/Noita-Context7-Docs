---
title: Steam Receptacle Building
category: entities
---

# Steam Receptacle Building

This entity defines a building that acts as a receptacle for steam. When steam is detected within its defined area, it triggers a Lua script.

## Key Components

### MaterialAreaCheckerComponent

This component is responsible for detecting specific materials within a defined area.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `area_aabb.min_x`   | Minimum X-coordinate of the detection area.                              |
| `area_aabb.max_x`   | Maximum X-coordinate of the detection area.                              |
| `area_aabb.min_y`   | Minimum Y-coordinate of the detection area.                              |
| `area_aabb.max_y`   | Maximum Y-coordinate of the detection area.                              |
| `update_every_x_frame` | How often the checker updates (1 means every frame).                     |
| `material`          | The primary material to look for (e.g., "steam").                        |
| `material2`         | A secondary material to look for (e.g., "smoke").                        |
| `look_for_failure`  | Whether to trigger on failure to find materials (0 means no).            |
| `kill_after_message`| Whether to destroy the entity after a message is sent (1 means yes).     |

### LuaComponent

This component links the material detection to a specific Lua script.

| Attribute                               | Description                                                              |
| :-------------------------------------- | :----------------------------------------------------------------------- |
| `script_material_area_checker_success`  | The path to the Lua script to execute when materials are detected.       |

## Associated Scripts

*   `data/scripts/buildings/receptacle_steam.lua`: This script is executed when the `MaterialAreaCheckerComponent` successfully detects the specified materials within its area. The exact functionality of this script is not detailed here but would typically involve actions related to the presence of steam.