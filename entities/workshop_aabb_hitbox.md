---
title: Workshop AABB Hitbox
category: entities
---

# Workshop AABB Hitbox

This entity defines the bounding box for the workshop area in Noita. It's primarily used for collision detection and defining the interactive space of the workshop.

## Key Components

### HitboxComponent

This component defines the physical boundaries of the entity.

| Attribute   | Value   | Description                                     |
| :---------- | :------ | :---------------------------------------------- |
| `aabb_min_x`| `-453`  | The minimum X-coordinate of the bounding box.   |
| `aabb_min_y`| `-44`   | The minimum Y-coordinate of the bounding box.   |
| `aabb_max_x`| `531`   | The maximum X-coordinate of the bounding box.   |
| `aabb_max_y`| `166`   | The maximum Y-coordinate of the bounding box.   |

## Entity Tags

*   `workshop_aabb`: This tag identifies the entity as the bounding box for the workshop.