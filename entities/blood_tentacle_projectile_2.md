---
title: Blood Tentacle Projectile 2
category: entities
---

# Blood Tentacle Projectile 2

This document describes the `bloodtentacle_2.xml` entity, which defines a projectile used by the blood tentacle in Noita.

## Sprite Component

The `SpriteComponent` defines the visual appearance of the projectile.

### Key Attributes:

*   **`image_file`**: `data/entities/projectiles/tentacle/bloodtentacle_2.png` - Specifies the texture file for the projectile's sprite.
*   **`offset_x`**: `0` - The horizontal offset of the sprite from the entity's origin.
*   **`offset_y`**: `4.5` - The vertical offset of the sprite from the entity's origin.
*   **`z_index`**: `0.82` - Controls the rendering order of the sprite, with higher values appearing on top.

## Entity Structure

The entity is a simple projectile with only a `SpriteComponent`. This suggests that its behavior and other properties are likely defined by the entity that spawns it or by other components not explicitly listed in this minimal XML.

```xml
<Entity >
   
  <SpriteComponent 
    image_file="data/entities/projectiles/tentacle/bloodtentacle_2.png" 
    offset_x="0"
    offset_y="4.5"
    update_transform="0"
    update_transform_rotation="0" 
	z_index="0.82"
	>
  </SpriteComponent>
  
</Entity>
```