---
title: Spruce Tree 3 Entity
category: entities
---

---

# Spruce Tree 3 Entity

This document describes the `tree_spruce_3.xml` entity, representing a spruce tree in Noita. It's primarily a visual element with basic physics.

## Key Components and Attributes

### Entity
- **name**: `unknown` (This is a placeholder and might be intended to be more descriptive).
- **tags**: `vegetation`, `pixelsprite` (Indicates its nature as plant life and a sprite-based object).

### PixelSpriteComponent
This component defines the visual representation of the tree.
- **_enabled**: `1` (The sprite component is active).
- **image_file**: `data/vegetation/tree_spruce_3.png` (Path to the sprite image).
- **anchor_x**: `35` (Horizontal anchor point for the sprite).
- **anchor_y**: `132` (Vertical anchor point for the sprite).
- **clean_overlapping_pixels**: `0` (Disables cleaning of overlapping pixels, which might be relevant for specific sprite layering).

### SimplePhysicsComponent
This component handles basic physics properties.
- **can_go_up**: `0` (The tree cannot move upwards).

### VelocityComponent
This component is present but has no specific attributes defined, suggesting it's a default component for entities that might have velocity.