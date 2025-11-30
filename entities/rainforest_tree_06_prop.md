---
title: Rainforest Tree 06 Prop
category: guides
---

<Entity 
  name="rainforest_tree_06" 
  tags="vegetation,pixelsprite" >
  
  <Base file="data/entities/props/base_coalmine_structure.xml" >

    <PixelSpriteComponent 
      image_file="data/vegetation/swamp_cropped_06.png" 
      anchor_x="8" 
      anchor_y="89"
    >
    </PixelSpriteComponent>

  </Base>

</Entity>
```

---
title: Rainforest Tree 06 Prop
category: entities
---

# Rainforest Tree 06 Prop

This entity defines a prop representing a tree in a rainforest biome. It inherits its base functionality from `base_coalmine_structure.xml` and utilizes a `PixelSpriteComponent` for its visual representation.

## Key Attributes

*   **`name`**: `rainforest_tree_06` - The unique identifier for this entity.
*   **`tags`**: `vegetation,pixelsprite` - Indicates that this entity is a piece of vegetation and uses pixel art for its sprite.

## Base Entity

*   **`Base file`**: `data/entities/props/base_coalmine_structure.xml` - This entity inherits properties and behaviors from the base coalmine structure. This suggests it might share some structural or collision properties, though the visual aspect is overridden.

## Pixel Sprite Component

*   **`image_file`**: `data/vegetation/swamp_cropped_06.png` - Specifies the image file used for the tree's sprite.
*   **`anchor_x`**: `8` - The horizontal anchor point for the sprite.
*   **`anchor_y`**: `89` - The vertical anchor point for the sprite. This high value suggests the anchor is near the bottom of the sprite, likely for proper placement on the ground.