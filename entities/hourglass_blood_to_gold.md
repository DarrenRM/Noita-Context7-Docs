---
title: Hourglass (Blood to Gold)
category: entities
---

# Hourglass (Blood to Gold)

This entity represents a functional hourglass that converts blood into gold. It utilizes a combination of components to detect blood and perform the material conversion.

## Key Components

### MagicConvertMaterialComponent

This component handles the core material conversion logic.

*   **`_tags`**: `enabled_by_liquid` - Indicates this component is active when a liquid is present.
*   **`_enabled`**: `0` - Initially disabled, likely activated by other components.
*   **`kill_when_finished`**: `1` - The entity will be destroyed once the conversion is complete.
*   **`steps_per_frame`**: `1` - Controls the speed of the conversion process.
*   **`from_material_tag`**: `[blood]` - Specifies the material to be converted.
*   **`to_material`**: `gold` - The material the source material will be converted into.
*   **`radius`**: `46` - The radius within which the conversion will occur.

### MaterialAreaCheckerComponent

This component is responsible for detecting the presence of the target material (blood).

*   **`_tags`**: `disabled_by_liquid` - Indicates this component is inactive when a liquid is present (likely to avoid interference with the conversion).
*   **`area_aabb.min_x`**: `-16`
*   **`area_aabb.max_x`**: `16`
*   **`area_aabb.min_y`**: `0`
*   **`area_aabb.max_y`**: `8` - Defines the bounding box for material detection.
*   **`update_every_x_frame`**: `1` - How often the area is checked.
*   **`material`**: `blood` - The primary material to look for.
*   **`material2`**: `blood` - Can be used for secondary material checks, here it's the same.

### LuaComponent

This component links the `MaterialAreaCheckerComponent`'s success to a specific script.

*   **`_tags`**: `disabled_by_liquid` - Similar to the `MaterialAreaCheckerComponent`, this is inactive when liquid is present.
*   **`script_material_area_checker_success`**: `data/scripts/buildings/hourglass_material_check.lua` - The script executed when the `MaterialAreaCheckerComponent` successfully finds the target material. This script likely triggers the `MagicConvertMaterialComponent`.