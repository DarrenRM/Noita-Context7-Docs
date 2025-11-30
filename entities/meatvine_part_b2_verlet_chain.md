---
title: Meatvine Part B2 Verlet Chain
category: entities
---

# Meatvine Part B2 Verlet Chain

This entity defines a segment of the "meatvine" verlet chain, specifically the 'B2' variant. It primarily consists of a sprite component to render its visual appearance.

## Sprite Component

The `SpriteComponent` dictates how this entity is visually represented in the game.

### Key Attributes:

*   **`image_file`**: Specifies the sprite's image file. In this case, it points to `data/entities/verlet_chains/meatvine/vine_parts/vine_b_2.xml`. This likely contains the actual sprite data or references to it.
*   **`offset_x`**: Horizontal offset for the sprite. Set to `0`.
*   **`offset_y`**: Vertical offset for the sprite. Set to `1.5`.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. Set to `0` (false), meaning it's likely managed by the verlet chain system directly.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. Set to `0` (false), indicating its rotation is also likely managed by the verlet chain system.

```xml
<Entity >
  <SpriteComponent 
    image_file="data/entities/verlet_chains/meatvine/vine_parts/vine_b_2.xml" 
    offset_x="0"
    offset_y="1.5"
    update_transform="0"
    update_transform_rotation="0" >
  </SpriteComponent>
</Entity>
```