---
title: Physics Chair 2
category: entities
---

# Physics Chair 2

This document describes the `physics_chair_2.xml` entity, a basic physics-enabled prop in Noita.

## Entity Definition

The core of this entity is its `Base` component, which inherits functionality from `data/entities/base_item_physics2.xml`. This indicates it's a physics-driven item with standard properties.

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the chair.

*   **`image_file`**: `data/props_gfx/chair_2.png` - Specifies the sprite used for the chair.
*   **`material`**: `wood_prop` - Assigns the "wood\_prop" material, influencing its interaction with physics and other game elements.