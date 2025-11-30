---
title: Holiday Workshop Building
category: entities
---

# Holiday Workshop Building

This document describes the `workshop_tree_holiday.xml` entity, which represents a holiday-themed workshop building in Noita.

## Key Components

### Entity Tags

*   `workshop`: Identifies this entity as a workshop.
*   `workshop_show_hint`: Indicates that this workshop should display a hint to the player.

### HitboxComponent

This component defines the collision area of the workshop.

| Attribute   | Value   | Description                               |
| :---------- | :------ | :---------------------------------------- |
| `aabb_min_x` | `-200`  | Minimum X-coordinate of the bounding box. |
| `aabb_min_y` | `-64`   | Minimum Y-coordinate of the bounding box. |
| `aabb_max_x` | `200`   | Maximum X-coordinate of the bounding box. |
| `aabb_max_y` | `64`    | Maximum Y-coordinate of the bounding box. |