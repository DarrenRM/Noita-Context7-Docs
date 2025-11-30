---
title: Temple Area Checker Vertical Stub
category: entities
---

---

# Temple Area Checker Vertical Stub

This entity defines a vertical area checker used in temples, primarily for detecting leaks or ensuring structural integrity.

## Key Components

### MaterialAreaCheckerComponent

This component defines the area to be checked and the materials that should be present within it.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `area_aabb.min_x`   | Minimum X-coordinate of the bounding box.                                   |
| `area_aabb.min_y`   | Minimum Y-coordinate of the bounding box.                                   |
| `area_aabb.max_x`   | Maximum X-coordinate of the bounding box.                                   |
| `area_aabb.max_y`   | Maximum Y-coordinate of the bounding box.                                   |
| `material`          | The primary material expected within the area.                              |
| `material2`         | A secondary material expected within the area.                              |
| `kill_after_message`| If set to "1", the entity will be destroyed after a message is triggered. |

### LuaComponent

This component links the area checker to a Lua script that handles the logic when the area check fails.

| Attribute                                      | Description                                                                                             |
| :--------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_material_area_checker_failed`          | The path to the Lua script executed when the `MaterialAreaCheckerComponent` fails its check.          |

## Usage

This entity is typically placed in temple structures to monitor specific vertical sections. If the expected materials are not found within the defined `area_aabb`, the script specified in `script_material_area_checker_failed` will be executed. This is often used to detect unintended openings or "leaks" in temple construction.