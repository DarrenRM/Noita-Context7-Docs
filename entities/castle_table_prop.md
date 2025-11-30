---
title: Castle Table Prop
category: entities
---

# Castle Table Prop

This document describes the `furniture_castle_table.xml` entity, a prop commonly found in castle environments within Noita.

## Key Attributes

The `furniture_castle_table.xml` entity is a simple prop with the following key attributes:

*   **`name`**: `unknown` (This is a placeholder and can be customized for specific instances).
*   **`Base file`**: `data/entities/base_item_physics2.xml` - Inherits physics and collision properties from a generic physics-based item.

### `PhysicsImageShapeComponent`

This component defines the visual representation and physical properties of the table.

*   **`image_file`**: `data/props_gfx/furniture_castle_table.png` - Specifies the sprite used for the table.
*   **`material`**: `rock_box2d` - Defines the physical material, influencing its interaction with physics (e.g., how it breaks or reacts to explosions).