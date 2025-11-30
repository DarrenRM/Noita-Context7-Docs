---
title: Orb Room Material Checker
category: entities
---

# Orb Room Material Checker

This entity defines a checker within an orb room that monitors a specific area for the presence of a particular material. If the material is detected, it triggers a failure condition.

## Key Components

### MaterialAreaCheckerComponent

This component defines the area to be checked and the material to look for.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `area_aabb.min_x` | Minimum X-coordinate of the bounding box for the check area.             |
| `area_aabb.min_y` | Minimum Y-coordinate of the bounding box for the check area.             |
| `area_aabb.max_x` | Maximum X-coordinate of the bounding box for the check area.             |
| `area_aabb.max_y` | Maximum Y-coordinate of the bounding box for the check area.             |
| `material`       | The primary material to detect within the specified area.                |
| `material2`      | An optional secondary material to detect. If set to the same as `material`, it checks for either. |
| `kill_after_message` | If set to "1", the entity will be destroyed after a failure message is displayed. |
| `look_for_failure` | If set to "0", the component actively looks for the specified material to trigger a failure. |

### LuaComponent

This component links the material checker to a Lua script that handles the failure logic.

| Attribute                               | Description                                                                                             |
| :-------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_material_area_checker_failed` | The path to the Lua script executed when the `MaterialAreaCheckerComponent` detects a failure condition. |

## Example Usage

The provided XML defines a checker for the material "blood" within a specific rectangular area. If "blood" is found in this area, the `temple_check_for_leaks.lua` script will be executed, and the checker entity will be destroyed if `kill_after_message` is set to "1".