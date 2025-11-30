---
title: Base Physics Prop Entity
category: entities
---

# Base Physics Prop Entity

This document describes the base entity for physics-enabled props in Noita, serving as a foundation for various interactive objects within the game world.

## Key Components

### PhysicsBody2Component
This component governs the physical behavior of the entity.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `allow_sleep`       | Determines if the physics body can enter a sleep state to save performance. |
| `angular_damping`   | Reduces rotational velocity over time.                                      |
| `linear_damping`    | Reduces linear velocity over time.                                          |
| `kill_entity_after_initialized` | If set to 1, the entity is removed from the game after its physics are initialized. |

### PhysicsImageShapeComponent
This component defines the visual representation and collision shape of the physics body.

| Attribute   | Description                                                                 |
| :---------- | :-------------------------------------------------------------------------- |
| `is_root`   | Indicates if this shape is the primary one for the physics body.            |
| `centered`  | If true, the image is centered on the entity's origin.                      |
| `image_file`| Path to the image file used for the sprite and collision shape.             |
| `material`  | The material type, affecting interactions with other physics objects.       |