---
title: Workshop Spell Visualizer
category: entities
---

# Workshop Spell Visualizer

This entity represents a visualizer for spells within the Noita workshop. It primarily defines a hitbox for interaction.

## Key Components

### HitboxComponent

This component defines the physical boundaries of the spell visualizer.

| Attribute   | Value   | Description                               |
| :---------- | :------ | :---------------------------------------- |
| `aabb_min_x` | -64     | Minimum X-coordinate of the bounding box. |
| `aabb_min_y` | -48     | Minimum Y-coordinate of the bounding box. |
| `aabb_max_x` | 64      | Maximum X-coordinate of the bounding box. |
| `aabb_max_y` | 48      | Maximum Y-coordinate of the bounding box. |

## Tags

*   `workshop_spell_visualizer`: Identifies this entity as a spell visualizer for the workshop.