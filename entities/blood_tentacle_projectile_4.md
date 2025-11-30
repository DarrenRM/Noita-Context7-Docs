---
title: Blood Tentacle Projectile 4
category: entities
---

---

# Blood Tentacle Projectile 4

This document describes the `bloodtentacle_4.xml` entity, which defines a specific projectile used by the blood tentacle in Noita.

## Sprite Component

The `SpriteComponent` defines the visual representation of the projectile.

### Key Attributes:

*   **image\_file**: `data/entities/projectiles/tentacle/bloodtentacle_4.png` - Specifies the texture file for the projectile's sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite from the entity's origin.
*   **offset\_y**: `4.5` - Vertical offset of the sprite from the entity's origin.
*   **update\_transform**: `0` - Indicates whether the sprite's transform (position, rotation, scale) should be updated automatically. `0` means it's static relative to the entity.
*   **update\_transform\_rotation**: `0` - Indicates whether the sprite's rotation should be updated automatically. `0` means it's static relative to the entity.
*   **z\_index**: `0.83` - Determines the rendering order of the sprite. Higher values are rendered on top.