---
title: Tentacle Projectile 2B
category: entities
---

# Tentacle Projectile 2B

This document describes the `tentacle_2b.xml` entity, which defines a specific type of tentacle projectile in Noita.

## Entity Definition

The core of this entity is the `<Entity>` tag.

### Key Components

*   **SpriteComponent**: This component defines the visual representation of the projectile.
    *   `image_file`: Specifies the texture file used for the sprite (`data/entities/projectiles/tentacle/tentacle_2b.png`).
    *   `offset_x`: Horizontal offset for the sprite.
    *   `offset_y`: Vertical offset for the sprite.
    *   `update_transform`: Controls whether the sprite's transform is updated.
    *   `update_transform_rotation`: Controls whether the sprite's rotation is updated.