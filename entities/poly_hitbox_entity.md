---
title: Poly Hitbox Entity
category: entities
---

# Poly Hitbox Entity

This entity defines a hitbox component that prevents polymorphing within its bounds. It's typically used for specific areas or objects where polymorphing should be disabled.

## Key Components

### HitboxComponent

This component defines the physical boundaries of the entity.

| Attribute   | Value   | Description                                     |
| :---------- | :------ | :---------------------------------------------- |
| `aabb_min_x` | `-320`  | Minimum X-coordinate of the bounding box.       |
| `aabb_min_y` | `-320`  | Minimum Y-coordinate of the bounding box.       |
| `aabb_max_x` | `320`   | Maximum X-coordinate of the bounding box.       |
| `aabb_max_y` | `320`   | Maximum Y-coordinate of the bounding box.       |

## Key Tags

### `no_polymorphing_allowed`

This tag, when applied to an entity, prevents the player from polymorphing within the area defined by its hitbox.