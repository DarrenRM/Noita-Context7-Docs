---
title: Physics Skull 02 Prop
category: entities
---

# Physics Skull 02 Prop

This document describes the `physics_skull_02.xml` entity, a prop in Noita that utilizes physics.

## Entity Definition

The core of this entity is defined by its `name` attribute.

*   **name**: `unknown` (This is a placeholder and might be intended to be more descriptive.)

## Base Entity

This entity inherits properties from a base physics item.

*   **Base file**: `data/entities/base_item_physics2.xml`

## Physics Component

The `PhysicsImageShapeComponent` defines the physical properties and visual representation of the prop.

### PhysicsImageShapeComponent Attributes

*   **image_file**: `data/props_gfx/skull_02.png`
    *   Specifies the sprite used for the prop's visual appearance.
*   **material**: `bone_box2d`
    *   Determines the physical material properties (e.g., density, friction) for physics interactions. This material is likely defined elsewhere in the game's data.