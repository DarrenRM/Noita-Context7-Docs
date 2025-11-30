---
title: Remove Ground Projectile
category: entities
---

# Remove Ground Projectile

This entity defines a projectile that converts solid ground materials into air within a specified radius. It's primarily used for clearing terrain.

## Entity Components

### MagicConvertMaterialComponent

This component handles the material conversion logic.

*   **`kill_when_finished`**: `1` - The projectile will be destroyed once its conversion process is complete.
*   **`from_material_tag`**: `"[solid]"` - Specifies that the component targets materials tagged as "solid".
*   **`steps_per_frame`**: `5` - The number of conversion steps to perform per game frame. Higher values lead to faster conversion.
*   **`to_material`**: `"air"` - The material that the targeted `from_material_tag` will be converted into.
*   **`clean_stains`**: `1` - Removes any stains present on the converted materials.
*   **`is_circle`**: `1` - The conversion area is a circle.
*   **`radius`**: `256` - The radius of the circular conversion area in pixels.
*   **`loop`**: `0` - The conversion process will not loop.