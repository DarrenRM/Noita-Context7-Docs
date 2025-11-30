---
title: Dark Vine Part A7
category: entities
---

# Dark Vine Part A7

This entity defines a single segment of a dark vine, specifically the 'A7' variant. It's a visual component that contributes to the overall structure of a verlet chain, likely used for environmental elements or enemy parts.

## Sprite Component

The `SpriteComponent` handles the visual representation of this vine segment.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/vines/vine_parts/vine_dark_a_7.xml`. This likely contains the actual sprite data or references to it.
*   **`offset_x`**: Horizontal offset of the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset of the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (false), meaning it's static relative to its parent entity.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (false), meaning it's static in rotation.

```xml
<SpriteComponent 
  image_file="data/entities/verlet_chains/vines/vine_parts/vine_dark_a_7.xml" 
  offset_x="0"
  offset_y="1.5"
  update_transform="0"
  update_transform_rotation="0" >
</SpriteComponent>
```