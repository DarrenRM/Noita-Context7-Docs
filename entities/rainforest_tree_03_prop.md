---
title: Rainforest Tree 03 Prop
category: entities
---

# Rainforest Tree 03 Prop

This document describes the `rainforest_tree_03.xml` entity, a prop used in Noita.

## Entity Definition

The core entity definition for this prop.

```xml
<Entity 
  name="unknown" 
  tags="vegetation,pixelsprite" >
  
  <Base file="data/entities/props/base_coalmine_structure.xml" >
    <!-- ... -->
  </Base>

</Entity>
```

### Key Attributes:

*   **`name`**: "unknown" - This is a placeholder and likely intended to be more descriptive.
*   **`tags`**: "vegetation,pixelsprite" - Indicates the entity is a piece of vegetation and uses a pixel sprite for its visual representation.

## Base Entity

This prop inherits its base functionality from `base_coalmine_structure.xml`.

```xml
<Base file="data/entities/props/base_coalmine_structure.xml" >
  <!-- ... -->
</Base>
```

### PixelSpriteComponent

This component defines the visual appearance of the prop.

```xml
<PixelSpriteComponent 
  image_file="data/vegetation/swamp_cropped_03.png" 
  anchor_x="12" 
  anchor_y="37"
>
</PixelSpriteComponent>
```

#### Key Attributes:

*   **`image_file`**: "data/vegetation/swamp_cropped_03.png" - Specifies the image file used for the sprite.
*   **`anchor_x`**: "12" - The horizontal anchor point for the sprite.
*   **`anchor_y`**: "37" - The vertical anchor point for the sprite.