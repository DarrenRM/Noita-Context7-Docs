---
title: Teleport Liquid Check Script
category: scripts
---

# Teleport Liquid Check Script

This script provides functions to enable or disable components of an entity based on whether it is currently within a liquid. This is commonly used for teleportation mechanics that are activated or deactivated by the presence of specific liquids.

## Core Functions

### `material_area_checker_failed( pos_x, pos_y )`

This function is called when the entity is *not* within a liquid.

*   **Purpose:** Disables components tagged with `"enabled_by_liquid"`.
*   **Parameters:**
    *   `pos_x`: The X-coordinate of the entity.
    *   `pos_y`: The Y-coordinate of the entity.

### `material_area_checker_success( pos_x, pos_y )`

This function is called when the entity *is* within a liquid.

*   **Purpose:** Enables components tagged with `"enabled_by_liquid"`.
*   **Parameters:**
    *   `pos_x`: The X-coordinate of the entity.
    *   `pos_y`: The Y-coordinate of the entity.

## Key Concepts

*   **`EntitySetComponentsWithTagEnabled( entity_id, tag, enabled )`**: This is the core Noita API function used by the script. It allows for enabling or disabling specific components of an entity based on a provided tag.
*   **`"enabled_by_liquid"` Tag**: This is a custom tag used within the Noita data to identify which components should be controlled by the liquid check. When this script runs, it targets components with this specific tag.

## Usage Example (Conceptual)

Imagine a teleport pad entity. You would configure this entity to use `material_area_checker_failed` and `material_area_checker_success` as its `OnAreaFailed` and `OnAreaSuccess` callbacks, respectively. Additionally, the teleportation logic itself (e.g., a `TeleportComponent`) would need to have the `"enabled_by_liquid"` tag.

*   If the teleport pad is *not* in liquid, the teleportation component is disabled.
*   If the teleport pad *is* in liquid, the teleportation component is enabled, allowing it to function.