---
title: Tongue 3 Projectile
category: entities
---

---

# Tongue 3 Projectile

This document describes the `tongue_3.xml` entity, which defines a projectile used by tentacles in Noita.

## Sprite Component

The `SpriteComponent` defines the visual representation of the projectile.

### Key Attributes:

*   **`image_file`**: Specifies the texture file for the sprite.
    *   Value: `data/entities/projectiles/tentacle/tongue_3.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `0`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `4.5`
*   **`update_transform`**: Controls whether the sprite's transform is updated.
    *   Value: `0` (Disabled)
*   **`update_transform_rotation`**: Controls whether the sprite's rotation is updated.
    *   Value: `0` (Disabled)

## Entity

The root element for the projectile definition.

### Key Elements:

*   **`SpriteComponent`**: As detailed above, this is the primary component defining the visual aspect of the projectile.

---