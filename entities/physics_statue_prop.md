---
title: Physics Statue Prop
category: entities
---

# Physics Statue Prop

This document describes the `physics_statue.xml` entity, which represents a physics-enabled statue prop in Noita.

## Entity Definition

The core of this entity is its `Base file="data/entities/base_item_physics2.xml"`, indicating it inherits physics properties from a base physics item.

### Key Components

*   **`PhysicsImageShapeComponent`**: This component defines the visual representation and physical shape of the statue.
    *   **`image_file`**: Specifies the texture used for the statue.
        *   `data/props_gfx/statue.png`: The default image file for the statue.
    *   **`material`**: Defines the physical material properties for collision and interaction.
        *   `templebrick_box2d`: The material assigned to this statue, likely influencing its density and friction.