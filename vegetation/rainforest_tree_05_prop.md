---
title: Rainforest Tree 05 Prop
category: guides
---

<Entity 
  name="rainforest_tree_05" 
  tags="vegetation,pixelsprite" >
  
  <Base file="data/entities/props/base_coalmine_structure.xml" >

    <PixelSpriteComponent 
      image_file="data/vegetation/swamp_cropped_05.png" 
      anchor_x="29" 
      anchor_y="89"
    >
    </PixelSpriteComponent>

  </Base>

</Entity>
```

---
title: Rainforest Tree 05 Prop
category: entities
---

# Rainforest Tree 05 Prop

This document describes the `rainforest_tree_05.xml` entity, a prop representing a tree in the rainforest biome.

## Entity Definition

The main entity is named `rainforest_tree_05` and is tagged as `vegetation` and `pixelsprite`.

```xml
<Entity 
  name="rainforest_tree_05" 
  tags="vegetation,pixelsprite" >
  
  </Entity>
```

## Base Entity Inheritance

This entity inherits from `base_coalmine_structure.xml`. This suggests it might share some fundamental properties with structures found in the coalmine, though its visual representation is distinct.

```xml
  <Base file="data/entities/props/base_coalmine_structure.xml" >
  </Base>
```

## Pixel Sprite Component

This component defines the visual appearance of the tree.

### Key Attributes:

*   **`image_file`**: Specifies the texture file used for the sprite.
    *   `data/vegetation/swamp_cropped_05.png`
*   **`anchor_x`**: The horizontal anchor point for the sprite.
    *   `29`
*   **`anchor_y`**: The vertical anchor point for the sprite.
    *   `89`

```xml
    <PixelSpriteComponent 
      image_file="data/vegetation/swamp_cropped_05.png" 
      anchor_x="29" 
      anchor_y="89"
    >
    </PixelSpriteComponent>