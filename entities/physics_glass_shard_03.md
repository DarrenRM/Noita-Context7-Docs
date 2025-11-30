---
title: Physics Glass Shard 03
category: entities
---

# Physics Glass Shard 03

This entity represents a physics-enabled glass shard prop in Noita. It's designed to break and interact with the game's physics engine.

## Key Attributes

*   **`tags`**: `mortal` - Indicates that this entity can be destroyed.
*   **`Base file`**: `data/entities/base_item_physics.xml` - Inherits core physics item properties.

### `PhysicsBodyComponent`

*   **`on_death_really_leave_body`**: `1` - Ensures the physics body remains after death, allowing for continued interaction.

### `PhysicsImageShapeComponent`

*   **`centered`**: `1` - Centers the sprite within its physics shape.
*   **`image_file`**: `data/props_gfx/glass_shard_03.png` - Specifies the visual sprite for the shard.
*   **`material`**: `glass_box2d` - Defines the physical material properties for collision and interaction.

### `LifetimeComponent`

*   **`lifetime`**: `360` - Sets the duration in seconds before the shard is automatically removed from the game.