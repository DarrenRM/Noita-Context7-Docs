---
title: Physics Bone 04 Prop
category: entities
---

# Physics Bone 04 Prop

This document describes the `physics_bone_04.xml` entity, a prop designed for use within the Noita game engine. It leverages a base physics entity to create a destructible object with visual representation.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: This indicates that `physics_bone_04.xml` inherits properties and functionality from the `base_item_physics2.xml` entity. This base likely provides core physics simulation, collision handling, and item-like behaviors.

### Physics Shape Component

*   **`PhysicsImageShapeComponent`**: This component defines the physical shape and visual representation of the entity using an image.
    *   **`image_file="data/props_gfx/bone_04.png"`**: Specifies the graphical asset used for this prop. This is the visual texture that will be rendered.
    *   **`material="bone_box2d"`**: Defines the physical material properties of the object. This influences how it interacts with the physics engine (e.g., friction, density, bounciness). The `box2d` suffix suggests it's configured for the Box2D physics engine.

## Summary

The `physics_bone_04.xml` entity is a simple prop that utilizes a base physics entity and a `PhysicsImageShapeComponent` to render a bone-like object with defined physical properties. Its primary function is to act as a destructible environmental element within the game world.