---
title: Big Bush 2 Entity
category: entities
---

# Big Bush 2 Entity

This document describes the `plant_bush_big_2.xml` entity, a large bush asset used in Noita.

## Entity Definition

The root element is `<Entity>`, defining a game object.

### Key Attributes:

*   **name**: "unknown" (This is a placeholder and could be more descriptive).
*   **tags**: "vegetation,pixelsprite" - Indicates the entity is a type of vegetation and uses a pixel sprite for its visual representation.

## Components

This entity utilizes several components to define its behavior and appearance.

### PixelSpriteComponent

This component handles the visual representation of the bush.

#### Key Attributes:

*   **image\_file**: `data/vegetation/lush_bush_02.png` - Specifies the image file used for the sprite.
*   **anchor\_x**: `24` - The horizontal anchor point for the sprite.
*   **anchor\_y**: `46` - The vertical anchor point for the sprite.
*   **clean\_overlapping\_pixels**: `0` - Disables the cleaning of overlapping pixels, which might be relevant for specific sprite art styles.

### SimplePhysicsComponent

This component defines basic physics properties.

#### Key Attributes:

*   **can\_go\_up**: `0` - Prevents the entity from moving upwards.

### VelocityComponent

This component is present but has no specific attributes defined, indicating it uses default velocity behavior.