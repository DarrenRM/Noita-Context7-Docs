---
title: Physics Stone 04
category: entities
---

# Physics Stone 04

This entity represents a basic physics-enabled stone prop. It's primarily defined by its visual representation and its physical properties.

## Key Components

### Base Entity

*   **`base_item_physics2.xml`**: Inherits core physics and item functionalities.

### Physics Image Shape Component

This component defines the visual appearance and physical collision shape of the stone.

*   **`image_file`**: `data/props_gfx/stone_04.png` - Specifies the sprite used for the stone.
*   **`material`**: `rock_box2d` - Defines the physical material properties, influencing how it interacts with the physics engine (e.g., friction, density).