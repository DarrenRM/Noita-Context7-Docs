---
title: Physics Stone 01
category: entities
---

# Physics Stone 01

This entity represents a basic physics-enabled stone prop. It's a simple object that interacts with the game's physics engine.

## Key Components

### `PhysicsImageShapeComponent`

This component defines the visual representation and physical properties of the stone.

*   **`image_file`**: `data/props_gfx/stone_01.png` - Specifies the texture used for the stone's appearance.
*   **`material`**: `rock_box2d` - Defines the physical material properties, influencing how it collides and interacts with other objects.