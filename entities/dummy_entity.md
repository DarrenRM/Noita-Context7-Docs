---
title: Dummy Entity
category: entities
---

# Dummy Entity

This entity serves as a foundational template for creating other entities in Noita. It's primarily used as a framework for generated objects, as indicated by its association with `release_child_entitites.lua`.

## Key Components

The `dummy_entity.xml` file defines a basic entity with the following essential components:

### `SimplePhysicsComponent`

This component provides basic physics properties to the entity. While not explicitly configured with parameters in this example, its presence suggests the entity can interact with the physics engine.

### `VelocityComponent`

This component allows the entity to have velocity. It's a standard component for any object that needs to move.

### `LifetimeComponent`

This component controls how long the entity exists.

*   **`lifetime`**: The base duration the entity will exist in frames (500 frames in this case).
*   **`randomize_lifetime.min`**: The minimum amount of time that can be randomly subtracted from the base lifetime (-200 frames).
*   **`randomize_lifetime.max`**: The maximum amount of time that can be randomly added to the base lifetime (200 frames).

This randomization ensures that generated entities don't all disappear at precisely the same moment, adding a touch of natural variation.

## Usage

As a "dummy" entity, its primary purpose is to be a blueprint. Developers can extend this entity by adding more components and properties to define the behavior and appearance of new, more complex entities.