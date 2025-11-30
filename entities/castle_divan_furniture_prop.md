---
title: Castle Divan Furniture Prop
category: entities
---

# Castle Divan Furniture Prop

This document describes the `furniture_castle_divan.xml` entity, a decorative furniture prop found in Noita.

## Entity Definition

The core of this entity is defined by its `Base file="data/entities/base_item_physics2.xml"`. This indicates it inherits physics properties and behaviors from a generic physics-based item.

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the prop.

*   **`image_file`**: `"data/props_gfx/furniture_castle_divan.png"`
    *   Specifies the graphical asset used for the divan.
*   **`material`**: `"rock_box2d"`
    *   Defines the physical material properties, influencing its interaction with the game's physics engine (e.g., density, friction).