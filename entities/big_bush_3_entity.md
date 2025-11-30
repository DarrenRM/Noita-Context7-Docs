---
title: Big Bush 3 Entity
category: entities
---

# Big Bush 3 Entity

This document describes the `plant_bush_big_3.xml` entity, a large bush asset used in Noita.

## Entity Definition

The core entity definition for the big bush.

```xml
<Entity 
  name="unknown" 
  tags="vegetation,pixelsprite" >
  
  <!-- ... components ... -->
  
</Entity>
```

*   **name**: "unknown" - This is a placeholder and could be more descriptive.
*   **tags**: `vegetation`, `pixelsprite` - Indicates the entity is a plant and uses pixel art.

## PixelSpriteComponent

Defines the visual representation of the bush.

```xml
<PixelSpriteComponent 
  _enabled="1" 
  image_file="data/vegetation/lush_bush_03.png" 
  anchor_x="24" 
  anchor_y="46"
  clean_overlapping_pixels="0"
>
</PixelSpriteComponent>
```

*   **_enabled**: `1` - The component is active.
*   **image\_file**: `data/vegetation/lush_bush_03.png` - Specifies the sprite image to use.
*   **anchor\_x**: `24` - The horizontal anchor point for the sprite.
*   **anchor\_y**: `46` - The vertical anchor point for the sprite.
*   **clean\_overlapping\_pixels**: `0` - Disables the cleaning of overlapping pixels, which might be relevant for specific sprite designs.

## SimplePhysicsComponent

Handles basic physics properties.

```xml
<SimplePhysicsComponent 
  can_go_up="0"
  >
</SimplePhysicsComponent >
```

*   **can\_go\_up**: `0` - The entity cannot move upwards.

## VelocityComponent

A standard component for entities that can have velocity.

```xml
<VelocityComponent />
```

This component is present but has no specific attributes defined, meaning it uses default values.