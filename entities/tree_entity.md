---
title: Tree Entity
category: entities
---

---

# Tree Entity

This document describes the `tree.xml` entity, a basic vegetation element in Noita. It's designed to be a static, non-interactive object within the game world.

## Key Components

### PixelSpriteComponent

This component defines the visual representation of the tree.

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `image_file`  | Path to the sprite image (`data/vegetation/tree_spruce_1.png`). |
| `anchor_x`    | X-coordinate of the sprite's anchor point.      |
| `anchor_y`    | Y-coordinate of the sprite's anchor point.      |
| `clean_overlapping_pixels` | Whether to clean overlapping pixels (set to `0` for this tree). |

### SimplePhysicsComponent

This component handles basic physics properties.

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `can_go_up`   | Determines if the entity can move upwards (set to `0` for this tree). |

### VelocityComponent

This component is present but has no specific attributes defined, indicating it's a placeholder or uses default velocity behavior.

## Entity Attributes

| Attribute | Description                                     |
|-----------|-------------------------------------------------|
| `name`    | Internal name of the entity (`unknown` in this case, likely a placeholder). |
| `tags`    | Comma-separated list of tags (`vegetation`, `pixelsprite`). |