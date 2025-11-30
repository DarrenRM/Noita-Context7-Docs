---
title: Blue Vine Part B2
category: entities
---

# Blue Vine Part B2

This entity defines a single segment of a blue vine, specifically the "B2" variant. It primarily consists of a sprite component that dictates its visual appearance.

## Sprite Component

The `SpriteComponent` is the core of this entity, defining how the vine segment looks.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/vines/vine_parts_blue/vine_b_2.xml`. This likely contains the actual sprite data or references to it.
*   **`offset_x`**: The horizontal offset of the sprite. Set to `0`.
*   **`offset_y`**: The vertical offset of the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0`, meaning it's static in this regard.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0`, meaning it's static in rotation.

```xml
<SpriteComponent 
  image_file="data/entities/verlet_chains/vines/vine_parts_blue/vine_b_2.xml" 
  offset_x="0"
  offset_y="1.5"
  update_transform="0"
  update_transform_rotation="0" >
</SpriteComponent>
```