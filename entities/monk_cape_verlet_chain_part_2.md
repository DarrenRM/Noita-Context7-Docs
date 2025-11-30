---
title: Monk Cape Verlet Chain Part 2
category: entities
---

# Monk Cape Verlet Chain Part 2

This document describes a component of the Monk Cape's verlet chain system in Noita, specifically `cape_verlet_2.xml`. This entity is responsible for rendering a part of the cape's visual representation.

## SpriteComponent

This component defines the visual appearance of the entity.

### Key Attributes:

*   **`image_file`**: Specifies the path to the sprite's image data.
    *   Value: `"data/entities/verlet_chains/monk_cape/parts/cape_2.xml"`
*   **`offset_x`**: The horizontal offset of the sprite from its entity's origin.
    *   Value: `"1"`
*   **`offset_y`**: The vertical offset of the sprite from its entity's origin.
    *   Value: `"12"`
*   **`z_index`**: Determines the rendering order of the sprite. Higher values are rendered on top.
    *   Value: `"1.3"`
*   **`update_transform`**: Controls whether the sprite's transform (position, rotation, scale) is updated automatically.
    *   Value: `"0"` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated automatically.
    *   Value: `"0"` (Disabled)

```xml
<Entity >
   
  <SpriteComponent 
    image_file="data/entities/verlet_chains/monk_cape/parts/cape_2.xml" 
    offset_x="1"
    offset_y="12"
	z_index="1.3"
    update_transform="0"
    update_transform_rotation="0" >
  </SpriteComponent>
  
</Entity>
```