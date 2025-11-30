---
title: Bush Entity - Lush Small 02
category: entities
---

# Bush Entity - Lush Small 02

This document describes the `plant_bush_2.xml` entity, representing a small, lush bush in Noita. It's primarily a visual element with basic physics.

## Entity Definition

The root `<Entity>` tag defines the basic properties of this game object.

### Key Attributes:

*   **name**: `unknown` - This is a placeholder and likely intended to be more descriptive.
*   **tags**: `vegetation,pixelsprite` - Indicates this entity is part of the game's vegetation and uses a pixel sprite for its visual representation.

## Components

This entity utilizes several components to define its behavior and appearance.

### PixelSpriteComponent

This component handles the visual rendering of the bush.

#### Key Attributes:

*   **_enabled**: `1` - The component is active.
*   **image\_file**: `data/vegetation/lush_bush_small_02.png` - Specifies the image file used for the sprite.
*   **anchor\_x**: `16` - The horizontal anchor point for the sprite.
*   **anchor\_y**: `30` - The vertical anchor point for the sprite.
*   **clean\_overlapping\_pixels**: `0` - Pixels are not cleaned up if they overlap.

### SimplePhysicsComponent

This component provides basic physics properties.

#### Key Attributes:

*   **can\_go\_up**: `0` - The entity cannot move upwards.

### VelocityComponent

This component is present but has no specific attributes defined, suggesting it might be a default component for entities that could potentially have velocity.

```xml
<Entity 
  name="unknown" 
  tags="vegetation,pixelsprite" >
  
  <PixelSpriteComponent 
    _enabled="1" 
    image_file="data/vegetation/lush_bush_small_02.png" 
    anchor_x="16" 
    anchor_y="30"
    clean_overlapping_pixels="0"
  >
  </PixelSpriteComponent>

  <SimplePhysicsComponent 
    can_go_up="0"
    >
  </SimplePhysicsComponent >
  
  <VelocityComponent />
  
</Entity>
```