---
title: Bush Entity - Lush Small 01
category: entities
---

# Bush Entity - Lush Small 01

This document describes the `plant_bush_1.xml` entity, representing a small, lush bush in Noita. It's primarily a visual element with basic physics.

## Entity Definition

The root `<Entity>` tag defines the basic properties of this game object.

### Key Attributes:

*   **name**: `unknown` (This is a placeholder and might be intended to be more descriptive).
*   **tags**: `vegetation`, `pixelsprite` (Indicates its role as plant life and its visual representation).

## Components

This entity utilizes several components to define its behavior and appearance.

### PixelSpriteComponent

This component handles the visual rendering of the bush.

#### Key Attributes:

*   **_enabled**: `1` (The component is active).
*   **image\_file**: `data/vegetation/lush_bush_small_01.png` (Specifies the sprite image used for this bush).
*   **anchor\_x**: `16` (Horizontal anchor point for the sprite).
*   **anchor\_y**: `30` (Vertical anchor point for the sprite).
*   **clean\_overlapping\_pixels**: `0` (Disables cleaning of overlapping pixels, which might be relevant for specific sprite art).

### SimplePhysicsComponent

This component defines basic physical properties.

#### Key Attributes:

*   **can\_go\_up**: `0` (The bush cannot move upwards).

### VelocityComponent

This component is present but has no specific attributes defined, suggesting it might be a default component for entities that could potentially have velocity, even if this specific one doesn't actively use it.

```xml
<Entity 
  name="unknown" 
  tags="vegetation,pixelsprite" >
  
  <PixelSpriteComponent 
    _enabled="1" 
    image_file="data/vegetation/lush_bush_small_01.png" 
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