---
title: Tiny Physics Wheel Prop
category: data/entities
---

# Tiny Physics Wheel Prop

This document describes the `physics_wheel_tiny.xml` entity, a small, physics-enabled prop in Noita. It's designed to be a simple, interactable object with basic physics properties.

## Key Components and Attributes

### Base Entity

The entity inherits from `data/entities/base_item_physics.xml`, providing fundamental physics and item-related functionalities.

### PhysicsImageShapeComponent

This component defines the visual representation and physical material of the prop.

| Attribute     | Description                                     | Value Example        |
| :------------ | :---------------------------------------------- | :------------------- |
| `image_file`  | Path to the sprite for the prop.                | `data/props_gfx/wheel_tiny.png` |
| `material`    | The physical material type for physics simulation. | `wood_prop`          |

### PhysicsBodyComponent

Configures the physical behavior of the prop.

| Attribute               | Description                                                              | Value Example |
| :---------------------- | :----------------------------------------------------------------------- | :------------ |
| `allow_sleep`           | Whether the body can enter a sleeping state when inactive.               | `1`           |
| `angular_damping`       | Resistance to rotational motion.                                         | `0.01`        |
| `gridworld_box2d`       | Whether to use Box2D physics within the grid world.                       | `0`           |
| `linear_damping`        | Resistance to linear motion.                                             | `0.1`         |
| `randomize_init_velocity` | Whether to apply a random initial velocity upon spawning.                | `1`           |

### PhysicsJointComponent

This component attaches the wheel to a fixed point, simulating a pivot.

| Attribute         | Description                                                              | Value Example |
| :---------------- | :----------------------------------------------------------------------- | :------------ |
| `nail_to_wall`    | If `1`, the joint will be fixed to the environment.                      | `1`           |
| `pos_x`, `pos_y`  | Offset from the entity's origin where the joint is placed.               | `11`, `11`    |
| `grid_joint`      | Whether to use grid-based joint positioning.                             | `1`           |
| `mMotorEnabled`   | Enables a motor for the joint, allowing for controlled rotation.         | `1`           |
| `mMotorSpeed`     | The target speed for the joint motor.                                    | `0.5`         |
| `mMaxMotorTorque` | The maximum torque the motor can apply to achieve the target speed.      | `100`         |

### CameraBoundComponent

Manages the entity's visibility and behavior relative to the camera.

| Attribute   | Description                                                              | Value Example |
| :---------- | :----------------------------------------------------------------------- | :------------ |
| `max_count` | Maximum number of this entity type that can be active within the camera's view. | `100`         |
| `distance`  | The maximum distance from the camera at which the entity can be rendered. | `1000`        |

### DamageModelComponent

Defines how the entity handles damage and its destruction.

| Attribute                 | Description                                                              | Value Example |
| :------------------------ | :----------------------------------------------------------------------- | :------------ |
| `hp`                      | Hit points of the entity.                                                | `99999`       |
| `fire_damage_amount`      | The amount of damage taken from fire per tick.                           | `0.2`         |
| `materials_damage`        | Whether the entity can be damaged by colliding materials.                | `1`           |
| `blood_material`          | The material that is spawned when the entity takes damage.               | `wood`        |
| `drop_items_on_death`     | Whether to drop items when destroyed.                                    | `0`           |
| `falling_damages`         | Whether the entity takes damage from falling.                            | `0`           |
| `critical_damage_resistance` | Resistance to critical damage.                                           | `1`           |

**Note:** The `mortal` tag on the root entity is crucial, as it enables the entity to explode or be destroyed in ways typical of living creatures, even though it's a prop.