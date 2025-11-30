---
title: Temple Statue 01 (Green) Prop
category: entities
---

# Temple Statue 01 (Green) Prop

This document details the `temple_statue_01_green.xml` entity, representing a green temple statue prop in Noita.

## Core Components

This entity is primarily defined by its physical properties and how it interacts with the game world.

### PhysicsBody2Component

Handles the physical behavior of the statue.

| Attribute      | Value   | Description                                     |
|----------------|---------|-------------------------------------------------|
| `angular_damping` | `0.1`   | Resistance to rotational movement.              |
| `init_offset_x`  | `11`    | Initial horizontal offset for physics.          |
| `init_offset_y`  | `29`    | Initial vertical offset for physics.            |
| `root_offset_x`  | `8`     | Horizontal offset for the physics root.         |
| `root_offset_y`  | `8`     | Vertical offset for the physics root.           |

### PhysicsImageShapeComponent

Defines the visual shape and material of the statue for physics interactions.

| Attribute    | Value                                  | Description                                     |
|--------------|----------------------------------------|-------------------------------------------------|
| `image_file` | `data/props_gfx/temple_statue_01_green.png` | Path to the sprite image.                       |
| `is_root`    | `1`                                    | Indicates this is the root of the physics shape. |
| `centered`   | `0`                                    | Image is not centered by default.               |
| `material`   | `rock_box2d_hard`                      | The physical material type.                     |
| `offset_x`   | `0`                                    | Horizontal offset for the image shape.          |
| `offset_y`   | `0`                                    | Vertical offset for the image shape.            |

### DamageModelComponent

Manages how the statue takes damage and its health.

| Attribute                   | Value   | Description                                         |
|-----------------------------|---------|-----------------------------------------------------|
| `hp`                        | `1200`  | Hit points of the statue.                           |
| `air_needed`                | `0`     | Does not require air to function/exist.             |
| `blood_material`            | `sand`  | Material produced when damaged (if any).            |
| `drop_items_on_death`       | `0`     | Does not drop items upon destruction.               |
| `falling_damages`           | `0`     | Does not take damage from falling.                  |
| `fire_damage_amount`        | `0`     | Does not take damage from fire.                     |
| `fire_probability_of_ignition` | `0`     | Cannot ignite from fire.                            |
| `critical_damage_resistance`| `0`     | No resistance to critical damage.                   |
| `blood_multiplier`          | `0.01`  | Multiplier for blood material generation.           |
| `is_on_fire`                | `0`     | Not initially on fire.                              |
| `materials_create_messages` | `0`     | Does not generate messages from material interactions. |
| `materials_damage`          | `0`     | Does not take damage from material interactions.    |
| `ui_force_report_damage`    | `1`     | Forces damage to be reported in the UI.             |

## Entity Tags

The following tags are applied to this entity:

*   `prop`: Indicates it's a decorative or interactive object.
*   `hittable`: Can be damaged by player attacks.
*   `mortal`: Can be destroyed.
*   `homing_target`: Can be targeted by homing projectiles.