---
title: Tongue Projectile Sprite
category: entities
---

# Tongue Projectile Sprite

This document describes the sprite component for the "tongue_0" projectile entity in Noita.

## SpriteComponent

This component defines the visual appearance of the projectile.

### Key Attributes:

*   **image\_file**: `data/entities/projectiles/tentacle/tongue_0.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `0` - Horizontal offset of the sprite from the entity's origin.
*   **offset\_y**: `4.5` - Vertical offset of the sprite from the entity's origin.
*   **update\_transform**: `0` - Indicates whether the sprite's transform should be updated automatically. `0` means it's static relative to the entity's base transform.
*   **update\_transform\_rotation**: `0` - Indicates whether the sprite's rotation should be updated automatically. `0` means it's static relative to the entity's base rotation.
*   **z\_index**: `0.8` - Determines the drawing order of the sprite. Higher values are drawn on top.