---
title: Sale Indicator Entity
category: entities
---

# Sale Indicator Entity

This entity defines the visual indicator used to signify a sale in Noita. It's a simple entity primarily composed of a `SpriteComponent`.

## SpriteComponent

This component handles the visual representation of the sale indicator.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the indicator.
    *   `data/ui_gfx/sale_indicator.png`
*   **`offset_x`**: Horizontal offset of the sprite.
    *   `5`
*   **`offset_y`**: Vertical offset of the sprite.
    *   `0`
*   **`alpha`**: Transparency of the sprite.
    *   `1` (fully opaque)
*   **`z_index`**: Determines the rendering order. Lower values are rendered behind higher values.
    *   `-1.5` (rendered behind most other game elements)