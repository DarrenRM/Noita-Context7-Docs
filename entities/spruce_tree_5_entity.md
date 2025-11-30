---
title: Spruce Tree 5 Entity
category: entities
---

# Spruce Tree 5 Entity

This document describes the `tree_spruce_5.xml` entity, representing a specific type of spruce tree in Noita.

## Entity Definition

The root element defines the entity with a `name` and `tags`.

*   **name**: `unknown` (This is a placeholder and might be intended to be more descriptive).
*   **tags**: `vegetation`, `pixelsprite` (Indicates it's a plant and uses pixel art).

## Key Components

### PixelSpriteComponent

This component handles the visual representation of the tree.

*   **_enabled**: `1` (Component is active).
*   **image\_file**: `data/vegetation/tree_spruce_5.png` (Path to the sprite image).
*   **anchor\_x**: `35` (Horizontal anchor point for the sprite).
*   **anchor\_y**: `132` (Vertical anchor point for the sprite).
*   **clean\_overlapping\_pixels**: `0` (Disables cleaning of overlapping pixels, potentially for a specific artistic effect).

### SimplePhysicsComponent

This component defines basic physics properties.

*   **can\_go\_up**: `0` (The entity cannot move upwards).

### VelocityComponent

This component is present but has no specific attributes defined, implying default velocity behavior.