---
title: Blue Torch Stand
category: entities
---

# Blue Torch Stand

This document describes the `physics_torch_stand_blue.xml` entity, which represents a blue torch stand in Noita. It details its physical properties, damage handling, and visual/particle effects.

## Core Components

The `physics_torch_stand_blue.xml` entity is built using several key components that define its behavior and appearance.

### `PhysicsBodyComponent`

This component governs the physical interactions of the torch stand.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `allow_sleep`       | Allows the physics body to sleep when not in active use, optimizing performance. |
| `angular_damping`   | Reduces rotational velocity over time.                                      |
| `fixed_rotation`    | If `1`, prevents the object from rotating.                                  |
| `is_bullet`         | If `1`, treats the object as a projectile.                                  |
| `linear_damping`    | Reduces linear velocity over time.                                          |
| `auto_clean`        | If `1`, the entity is automatically removed when it's no longer needed.     |
| `update_entity_transform` | If `1`, the entity's transform is updated based on physics.                 |
| `on_death_leave_physics_body` | If `1`, leaves a physics body behind when destroyed.                      |

### `PhysicsImageShapeComponent`

Defines the physical shape of the torch stand using an image.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `body_id`     | Links this shape to a specific `PhysicsBodyComponent`.                   |
| `centered`    | If `1`, the image is centered on the physics body.                       |
| `image_file`  | Path to the image file used for the shape.                               |
| `material`    | The material type of the physics shape, affecting interactions.          |

### `DamageModelComponent`

Manages how the torch stand takes damage and its reactions.

| Attribute                   | Description                                                                                             |
| :-------------------------- | :------------------------------------------------------------------------------------------------------ |
| `hp`                        | The hit points of the torch stand.                                                                      |
| `air_needed`                | If `1`, the entity requires air to survive.                                                             |
| `blood_material`            | The material that is produced when the entity takes damage (e.g., "fire").                              |
| `drop_items_on_death`       | If `1`, items are dropped when the entity dies.                                                         |
| `falling_damage_damage_max` | Maximum damage dealt from falling.                                                                      |
| `falling_damage_damage_min` | Minimum damage dealt from falling.                                                                      |
| `falling_damage_height_max` | Maximum height from which falling damage is calculated.                                                 |
| `falling_damage_height_min` | Minimum height from which falling damage is calculated.                                                 |
| `falling_damages`           | If `1`, the entity can take damage from falling.                                                        |
| `fire_damage_amount`        | The amount of damage dealt by fire.                                                                     |
| `fire_probability_of_ignition` | The chance of igniting from fire.                                                                       |
| `critical_damage_resistance` | Resistance to critical damage.                                                                          |
| `is_on_fire`                | If `1`, the entity is currently on fire.                                                                |
| `materials_create_messages` | If `1`, materials interacting with this entity create messages.                                         |
| `materials_damage`          | If `1`, materials interacting with this entity can cause damage.                                        |
| `ragdoll_material`          | The material used for the ragdoll when the entity is destroyed.                                         |
| `ui_report_damage`          | If `1`, damage taken is reported in the UI.                                                             |

## Child Entity: Light and Torch Effects

A nested `<Entity>` component handles the visual and functional aspects of the torch.

### `InheritTransformComponent`

Allows the child entity to inherit the transform (position, rotation, scale) of its parent.

| Attribute   | Description                                                               |
| :---------- | :------------------------------------------------------------------------ |
| `position.x` | X-coordinate offset relative to the parent.                               |
| `position.y` | Y-coordinate offset relative to the parent.                               |

### `LightComponent`

Defines the light emitted by the torch.

| Attribute       | Description                                                                                             |
| :-------------- | :------------------------------------------------------------------------------------------------------ |
| `_tags`         | Tags that determine when the light is active (e.g., `enabled_in_world`, `enabled_in_hand`, `fire`).     |
| `radius`        | The radius of the light emitted.                                                                        |
| `fade_out_time` | The time it takes for the light to fade out.                                                            |

### `TorchComponent`

This component specifically enables torch-like behavior.

| Attribute              | Description                                                                                             |
| :--------------------- | :------------------------------------------------------------------------------------------------------ |
| `_tags`                | Tags that determine when the torch functionality is active (e.g., `enabled_in_world`, `enabled_in_hand`). |
| `fire_audio_weight`    | Controls the intensity or volume of the fire sound effect.                                              |
| `suffocation_check_offset_y` | An offset used for checking suffocation conditions related to the torch's flame.                        |

### `SpriteAnimatorComponent`

This component is present but empty, suggesting it might be intended for future animation or is a placeholder.

### `Base file="data/entities/base_torch_particle.xml"`

This indicates that the entity inherits particle effects from a base torch particle definition.

#### `ParticleEmitterComponent` (Multiple instances)

These components define the particles emitted by the torch.

| Attribute              | Description