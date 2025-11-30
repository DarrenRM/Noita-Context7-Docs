---
title: Remove Liquid Entity
category: entities
---

# Remove Liquid Entity

This entity is designed to remove liquid from the game world. It utilizes the `MagicConvertMaterialComponent` to achieve this.

## Key Components and Attributes

### MagicConvertMaterialComponent

This component handles the conversion of materials within a specified area.

*   **`kill_when_finished`**: `1` - The entity will be destroyed once the material conversion process is complete.
*   **`from_material_tag`**: `"[liquid]"` - Specifies that this component targets any material tagged as `"[liquid]"`. This is a broad tag that encompasses most liquids in Noita.
*   **`steps_per_frame`**: `5` - Controls how many conversion steps are processed per game frame. A higher value can lead to faster conversion but might impact performance.
*   **`to_material`**: `"air"` - The material that the targeted `from_material_tag` will be converted into. In this case, liquids are converted into `air`, effectively removing them.
*   **`clean_stains`**: `1` - If set to `1`, this will also remove any stains left by the liquid.
*   **`is_circle`**: `1` - The conversion area is defined as a circle.
*   **`radius`**: `256` - The radius of the circular area in pixels where the material conversion will occur.
*   **`loop`**: `0` - The conversion process will run only once and not repeat.

## Usage

This entity is typically used in scenarios where you need to clear out large volumes of liquid, such as in specific puzzle rooms, boss arenas, or for environmental effects. The `radius` attribute makes it suitable for clearing substantial areas.