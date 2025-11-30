---
title: Verlet Chain Ribbon Part 1
category: entities
---

---

# Verlet Chain Ribbon Part 1

This document describes the configuration for the first part of a ribbon-likeverlet chain entity in Noita.

## Entity Configuration

The core of this entity is defined by its `SpriteComponent`.

### SpriteComponent

This component handles the visual representation of the entity.

| Attribute         | Value                                         | Description                                                                 |
| :---------------- | :-------------------------------------------- | :-------------------------------------------------------------------------- |
| `image_file`      | `data/entities/verlet_chains/ribbon/parts/image_1.xml` | Specifies the image file used for the sprite. This likely defines the visual appearance of the ribbon segment. |
| `offset_x`        | `1`                                           | Horizontal offset of the sprite from the entity's origin.                   |
| `offset_y`        | `1`                                           | Vertical offset of the sprite from the entity's origin.                     |
| `z_index`         | `-1.4`                                        | Determines the rendering order. A negative value places it behind other elements. |
| `update_transform`| `0`                                           | Disables automatic sprite transformation updates based on entity movement.  |
| `update_transform_rotation` | `0`                                   | Disables automatic sprite rotation updates based on entity rotation.        |