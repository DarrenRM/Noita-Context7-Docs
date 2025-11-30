---
title: Tree Leaf Entity
category: entities
---

# Tree Leaf Entity

This document describes the `tree_leaf.xml` entity, which represents a leaf from a tree in Noita. It's a basic entity primarily used for visual representation and interaction with physics.

## Key Components

### PixelSpriteComponent

This component defines the visual appearance of the tree leaf.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `image_file`   | Path to the sprite image (`data/vegetation/tree_leaf.png`). |
| `anchor_x`     | X-coordinate of the sprite's anchor point.      |
| `anchor_y`     | Y-coordinate of the sprite's anchor point.      |
| `clean_overlapping_pixels` | Whether to clean overlapping pixels (set to `0` for this entity). |

### SimplePhysicsComponent

This component handles basic physics properties.

| Attribute    | Description                                     |
|--------------|-------------------------------------------------|
| `can_go_up`  | Whether the entity can move upwards (set to `0`). |

### VelocityComponent

This component indicates that the entity has velocity properties, allowing it to move.

## Entity Attributes

| Attribute | Description                                     |
|-----------|-------------------------------------------------|
| `name`    | The internal name of the entity (`unknown` in this case, likely a placeholder). |
| `tags`    | A comma-separated list of tags associated with the entity (`vegetation`, `pixelsprite`). |