---
title: Physics Stone 02
category: entities
---

# Physics Stone 02

This entity represents a basic physics-enabled stone prop. It's a simple object that interacts with the game's physics engine.

## Key Components

### Base Entity

*   **`base_item_physics2.xml`**: Inherits core physics and item functionalities.

### Physics Image Shape Component

This component defines the visual representation and physical properties of the stone.

*   **`image_file`**: `data/props_gfx/stone_02.png` - Specifies the sprite used for the stone.
*   **`material`**: `rock_box2d` - Defines the physical material properties (e.g., friction, density) for collision and interaction.