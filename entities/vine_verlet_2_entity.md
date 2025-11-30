---
title: Vine Verlet 2 Entity
category: entities
---

# Vine Verlet 2 Entity

This document describes the `vine_verlet_2.xml` entity, which appears to be a visual component for a boss centipede's segmented body in Noita.

## Sprite Component

The primary component defining the visual representation of this entity.

### Key Attributes:

*   **`image_file`**: `data/entities/animals/boss_centipede/verlet_chains/verlet_2.xml`
    *   Specifies the image file used for the sprite. This likely contains the visual assets for a segment of the centipede.
*   **`offset_x`**: `0`
    *   Horizontal offset for the sprite.
*   **`offset_y`**: `3.5`
    *   Vertical offset for the sprite.
*   **`update_transform`**: `0`
    *   Disables automatic updating of the sprite's transform based on its parent entity.
*   **`update_transform_rotation`**: `0`
    *   Disables automatic updating of the sprite's rotation based on its parent entity.
*   **`z_index`**: `1.1`
    *   Determines the rendering order of this sprite relative to other entities. A higher `z_index` means it will be rendered on top.

## Entity Structure

The entity is a simple container for the `SpriteComponent`, indicating it's primarily a visual element without complex behaviors or physics attached directly to this specific XML definition.