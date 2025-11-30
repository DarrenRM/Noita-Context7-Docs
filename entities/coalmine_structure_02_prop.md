---
title: Coalmine Structure 02 Prop
category: guides
---

<Entity 
  name="coalmine_structure_02" 
  tags="vegetation,pixelsprite" >
  
  <Base file="data/entities/props/base_coalmine_structure.xml" >

    <PixelSpriteComponent 
      image_file="data/props_gfx/coalmine_structure_background_02.png" 
      anchor_x="5" 
      anchor_y="49"
    >
    </PixelSpriteComponent>

  </Base>
</Entity>
```

---
title: Coalmine Structure 02 Prop
category: entities
---

# Coalmine Structure 02 Prop

This entity defines a decorative prop for coalmine structures, specifically `coalmine_structure_02`. It inherits its base functionality from `base_coalmine_structure.xml` and utilizes a `PixelSpriteComponent` for its visual representation.

## Key Components and Attributes

### Entity
- **name**: `coalmine_structure_02` - Unique identifier for this entity.
- **tags**: `vegetation,pixelsprite` - Indicates it's a decorative element and uses pixel art.

### Base
- **file**: `data/entities/props/base_coalmine_structure.xml` - Inherits properties and behaviors from a base coalmine structure.

### PixelSpriteComponent
- **image_file**: `data/props_gfx/coalmine_structure_background_02.png` - Specifies the graphical asset used for this prop.
- **anchor_x**: `5` - The horizontal anchor point for the sprite.
- **anchor_y**: `49` - The vertical anchor point for the sprite.