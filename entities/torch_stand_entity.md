---
title: Torch Stand Entity
category: data
---

# Torch Stand Entity

This document describes the `physics_torch_stand.xml` entity, which represents a torch stand in Noita. It details its physical properties, damage model, and the light and particle effects it produces.

## Core Components

### `PhysicsBodyComponent`

This component defines the physical behavior of the torch stand.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `allow_sleep`       | Whether the physics body can enter a sleep state when inactive.             |
| `angular_damping`   | Resistance to rotational movement.                                          |
| `fixed_rotation`    | If true, the object cannot rotate.                                          |
| `is_bullet`         | If true, the object behaves like a bullet (e.g., passes through entities).  |
| `linear_damping`    | Resistance to linear movement.                                              |
| `auto_clean`        | If true, the entity is automatically removed when it's no longer needed.    |
| `update_entity_transform` | If true, the entity's transform is updated based on physics.              |
| `on_death_leave_physics_body` | If true, the physics body remains after the entity is destroyed.        |

### `PhysicsImageShapeComponent`

This component defines the physical shape of the torch stand using an image.

| Attribute    | Description                                                              |
| :----------- | :----------------------------------------------------------------------- |
| `body_id`    | The ID of the physics body this shape is associated with.                |
| `centered`   | If true, the image is centered on the entity's origin.                   |
| `image_file` | The path to the image file used for the shape.                           |
| `material`   | The material of the physics shape, affecting interactions.               |

### `DamageModelComponent`

This component governs how the torch stand takes damage and its reactions.

| Attribute                     | Description                                                                                             |
| :---------------------------- | :------------------------------------------------------------------------------------------------------ |
| `hp`                          | The hit points of the torch stand.                                                                      |
| `air_needed`                  | Whether the entity requires air to survive.                                                             |
| `blood_material`              | The material that is produced when the entity takes damage (e.g., "fire").                              |
| `drop_items_on_death`         | If true, items are dropped when the entity dies.                                                        |
| `falling_damage_damage_max`   | The maximum damage dealt by falling.                                                                    |
| `falling_damage_damage_min`   | The minimum damage dealt by falling.                                                                    |
| `falling_damage_height_max`   | The maximum height at which falling damage is applied.                                                  |
| `falling_damage_height_min`   | The minimum height at which falling damage is applied.                                                  |
| `falling_damages`             | If true, the entity can take damage from falling.                                                       |
| `fire_damage_amount`          | The amount of damage dealt by fire.                                                                     |
| `fire_probability_of_ignition`| The probability that the entity will ignite when exposed to fire.                                       |
| `materials_damage`            | If true, the entity takes damage from contact with certain materials.                                   |
| `ragdoll_material`            | The material used for the ragdoll when the entity dies.                                                 |

## Visual and Functional Elements

### `Entity` (Child Entity)

This nested entity contains components responsible for the torch's light and particle effects.

#### `InheritTransformComponent`

This component allows the child entity to inherit the transform (position, rotation, scale) of its parent.

| Attribute   | Description                                                               |
| :---------- | :------------------------------------------------------------------------ |
| `position.x`| The X-coordinate offset from the parent's origin.                         |
| `position.y`| The Y-coordinate offset from the parent's origin.                         |

#### `LightComponent`

This component adds a light source to the entity.

| Attribute       | Description                                                                                             |
| :-------------- | :------------------------------------------------------------------------------------------------------ |
| `_tags`         | Tags that determine when the light is active (e.g., `enabled_in_world`, `enabled_in_hand`, `fire`).     |
| `radius`        | The radius of the light emitted.                                                                        |
| `fade_out_time` | The time it takes for the light to fade out.                                                            |

#### `TorchComponent`

This component specifically enables torch-like behavior, including fire effects and audio.

| Attribute             | Description                                                                                             |
| :-------------------- | :------------------------------------------------------------------------------------------------------ |
| `_tags`               | Tags that determine when the torch functionality is active (e.g., `enabled_in_world`, `enabled_in_hand`). |
| `fire_audio_weight`   | Controls the intensity or volume of the fire sound effect.                                              |
| `suffocation_check_offset_y` | An offset used for checking if the torch is in an environment where it would suffocate (e.g., underwater). |

#### `SpriteAnimatorComponent`

This component is present but empty, suggesting it might be intended for future sprite animations or is a placeholder.

#### `Base file="data/entities/base_torch_particle.xml"`

This indicates that the entity inherits particle effects from a base torch particle definition.

##### `ParticleEmitterComponent` (Multiple instances)

These components define the emission of particles from the torch.

| Attribute           | Description                                                                                             |
| :------------------ | :------------------------------------------------------------------------------------------------------ |
| `x_pos_offset_min`  | The minimum X-axis offset for particle emission.                                                        |
| `x_pos_offset_max`  | The maximum X-axis offset for particle emission.                                                        |

These multiple `ParticleEmitterComponent` instances likely contribute to the visual spread and density of the fire particles emanating from the torch.