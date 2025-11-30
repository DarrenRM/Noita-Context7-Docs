---
title: Cord Verlet A 7
category: entities
---

# Cord Verlet A 7

This entity defines a specific part of a "verlet chain" cord, likely used for visual representation of physics-based ropes or chains in Noita.

## SpriteComponent

This component handles the visual appearance of the cord part.

### Key Attributes:

*   **`image_file`**: Specifies the image file used for the sprite. In this case, it points to `data/entities/verlet_chains/cords/cord_a_7.xml`, indicating a specific visual asset for this cord segment.
*   **`offset_x`**: Horizontal offset of the sprite.
*   **`offset_y`**: Vertical offset of the sprite.
*   **`update_transform`**: Controls whether the sprite's transform (position, scale, rotation) is updated. `0` means it's not automatically updated by the engine's transform system.
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated. `0` means it's not automatically updated.

```xml
<SpriteComponent 
  image_file="data/entities/verlet_chains/cords/cord_parts/cord_a_7.xml" 
  offset_x="0"
  offset_y="1.5"
  update_transform="0"
  update_transform_rotation="0" >
</SpriteComponent>
```