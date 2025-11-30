---
title: Rainforest Tree 02 Prop
category: entities
---

# Rainforest Tree 02 Prop

This document describes the `rainforest_tree_02.xml` entity, a prop representing a tree in the rainforest biome.

## Entity Definition

The core of this entity is defined by the `<Entity>` tag.

### Key Attributes:

*   **name**: `unknown` (This is a placeholder and likely should be more descriptive).
*   **tags**: `vegetation`, `pixelsprite` (Indicates its nature as a plant and a sprite-based object).

## Base Entity

This entity inherits properties from a base structure.

### Key Attributes:

*   **file**: `data/entities/props/base_coalmine_structure.xml` (Indicates inheritance from a base structure, though the name suggests a different biome, which might be an oversight or a shared base).

## Pixel Sprite Component

This component defines the visual representation of the tree.

### Key Attributes:

*   **image\_file**: `data/vegetation/swamp_cropped_02.png` (Specifies the sprite image used. Note the filename suggests a swamp, which might be inconsistent with the "rainforest" name).
*   **anchor\_x**: `9` (Horizontal anchor point for the sprite).
*   **anchor\_y**: `35` (Vertical anchor point for the sprite).