---
title: Big Bush 5 Entity
category: entities
---

# Big Bush 5 Entity

This document describes the `plant_bush_big_5.xml` entity, a large bush asset used in Noita.

## Entity Definition

The core entity definition for this bush.

```xml
<Entity 
  name="unknown" 
  tags="vegetation,pixelsprite" >
  
  <!-- ... components ... -->
  
</Entity>
```

*   **name**: "unknown" - This is a placeholder and could be more descriptive.
*   **tags**: `vegetation`, `pixelsprite` - Indicates its nature as a plant and a sprite-based object.

## PixelSpriteComponent

This component handles the visual representation of the bush.

```xml
<PixelSpriteComponent 
  _enabled="1" 
  image_file="data/vegetation/lush_bush_05.png" 
  anchor_x="24" 
  anchor_y="46"
  clean_overlapping_pixels="0"
>
</PixelSpriteComponent>
```

*   **_enabled**: `1` - The component is active.
*   **image\_file**: `data/vegetation/lush_bush_05.png` - Specifies the image asset used for the bush.
*   **anchor\_x**: `24` - The horizontal anchor point for the sprite.
*   **anchor\_y**: `46` - The vertical anchor point for the sprite.
*   **clean\_overlapping\_pixels**: `0` - Disables the cleaning of overlapping pixels, which might affect how the sprite blends with its surroundings.

## SimplePhysicsComponent

This component defines basic physics properties.

```xml
<SimplePhysicsComponent 
  can_go_up="0"
  >
</SimplePhysicsComponent >
```

*   **can\_go\_up**: `0` - The bush cannot move upwards.

## VelocityComponent

This component is present but has no specific attributes defined, implying default velocity behavior.

```xml
<VelocityComponent />
```