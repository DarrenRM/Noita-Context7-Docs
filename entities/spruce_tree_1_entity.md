---
title: Spruce Tree 1 Entity
category: entities
---

# Spruce Tree 1 Entity

This document describes the `tree_spruce_1.xml` entity, representing a spruce tree in Noita.

## Entity Definition

The root element defines the entity with a `name` and `tags`.

*   **name**: `unknown` (This is likely a placeholder and could be more descriptive).
*   **tags**: `vegetation`, `pixelsprite` (Indicates it's a plant and uses pixel art).

## Key Components

### PixelSpriteComponent

This component handles the visual representation of the tree.

*   **image\_file**: `data/vegetation/tree_spruce_1.png` (Specifies the sprite image).
*   **anchor\_x**: `35` (Horizontal anchor point for the sprite).
*   **anchor\_y**: `132` (Vertical anchor point for the sprite).
*   **clean\_overlapping\_pixels**: `0` (Disables cleaning of overlapping pixels, which might be relevant for sprite layering).

### SimplePhysicsComponent

This component defines basic physics properties.

*   **can\_go\_up**: `0` (The tree cannot move upwards).

### VelocityComponent

This component is present but has no specific attributes defined, implying default velocity behavior.