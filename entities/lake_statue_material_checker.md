---
title: Lake Statue Material Checker
category: entities
---

# Lake Statue Material Checker

This entity acts as a trigger that checks for the presence of a specific material within a defined area. It's commonly used in game logic to detect if a certain substance has filled a particular space, often for puzzle or progression mechanics.

## Key Components

### MaterialAreaCheckerComponent

This component defines the core functionality of the checker.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `area_aabb.min_x` | Minimum X-coordinate of the bounding box for material detection.            |
| `area_aabb.min_y` | Minimum Y-coordinate of the bounding box for material detection.            |
| `area_aabb.max_x` | Maximum X-coordinate of the bounding box for material detection.            |
| `area_aabb.max_y` | Maximum Y-coordinate of the bounding box for material detection.            |
| `material`       | The primary material to look for within the defined area.                   |
| `material2`      | An optional secondary material to also look for.                            |
| `kill_after_message` | If set to "1", the entity will be destroyed after a detection message. |
| `look_for_failure` | If set to "0", it only looks for success (material present), not failure. |

### LuaComponent

This component links the checker to a Lua script that handles the logic when the material is detected or not.

| Attribute                         | Description                                                                                             |
| :-------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_material_area_checker_failed` | The path to the Lua script executed when the material check *fails* (i.e., the material is not found). |