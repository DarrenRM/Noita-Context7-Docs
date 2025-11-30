---
title: Material Area Checker Test Entity
category: entities
---

# Material Area Checker Test Entity

This entity is a simple test case for the `MaterialAreaCheckerComponent`. It's designed to check if a specific material exists within a defined area.

## MaterialAreaCheckerComponent

This component is responsible for detecting materials within a specified bounding box.

### Key Attributes:

*   **`area_aabb.min_x`**: The minimum X-coordinate of the bounding box.
*   **`area_aabb.min_y`**: The minimum Y-coordinate of the bounding box.
*   **`area_aabb.max_x`**: The maximum X-coordinate of the bounding box.
*   **`area_aabb.max_y`**: The maximum Y-coordinate of the bounding box.
*   **`material`**: The primary material to check for within the area.
*   **`material2`**: An optional secondary material to check for.
*   **`kill_after_message`**: If set to "1", the entity will be removed after a message is triggered (likely related to the material check).

### Example Usage:

The provided XML defines a bounding box from `(-124, 0)` to `(109, 1)`. It checks for the presence of `templebrick_noedge_static` as both `material` and `material2`. If the condition is met, the entity is intended to be removed.