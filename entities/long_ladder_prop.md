---
title: Long Ladder Prop
category: entities
---

# Long Ladder Prop

This document describes the `ladder_long.xml` entity, a prop used in Noita.

## Entity Definition

The `ladder_long.xml` file defines a prop entity with the following key attributes:

*   **name**: `unknown` (This is a placeholder and can be customized).
*   **tags**: `prop`, `pixelsprite` (Indicates it's a visual prop and uses pixel art).

## Key Components

### PixelSpriteComponent

This component handles the visual representation of the ladder.

*   **image\_file**: `data/props_gfx/ladder_long.png` - Specifies the image asset used for the ladder.
*   **anchor\_x**: `5` - The horizontal anchor point for the sprite.
*   **anchor\_y**: `90` - The vertical anchor point for the sprite.

### SimplePhysicsComponent

This component defines basic physics properties.

*   **can\_go\_up**: `0` - This is a crucial setting, indicating that entities cannot ascend this ladder.

### VelocityComponent

This component is present but has no specific attributes defined in this snippet, suggesting it inherits default velocity behavior.