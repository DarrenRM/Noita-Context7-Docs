---
title: Small Physics Wheel Prop
category: data/entities
---

# Small Physics Wheel Prop

This document describes the `physics_wheel_small.xml` entity, a prop designed for use in Noita. It functions as a small, rotatable wheel that can be attached to surfaces.

## Core Components

### Base Entity

The entity inherits its fundamental properties from `data/entities/base_item_physics.xml`. This provides the basic framework for physics-enabled props.

### Physics Image Shape Component

This component defines the visual representation and physical properties of the wheel.

*   `image_file`: `data/props_gfx/wheel_small.png` - Specifies the sprite used for the wheel.
*   `material`: `wood_prop` - Assigns a material type, influencing its interaction with other physics objects and damage.

### Physics Body Component

This component governs the physical behavior of the wheel.

*   `angular_damping`: `0.01` - Controls how quickly rotational motion slows down.
*   `linear_damping`: `0.1` - Controls how quickly linear motion slows down.
*   `randomize_init_velocity`: `1` - Indicates that the object may start with a random initial velocity.
*   `gridworld_box2d`: `0` - Suggests it's not directly tied to the grid world's physics simulation in a standard way.

### Physics Joint Component

This component defines how the wheel is attached and its rotational behavior.

*   `nail_to_wall`: `1` - The wheel is fixed to a surface, acting like it's nailed.
*   `pos_x`: `20`, `pos_y`: `20` - The offset from the entity's origin where the joint is attached.
*   `grid_joint`: `1` - Indicates a joint that interacts with the grid-based physics.
*   `mMotorEnabled`: `1` - The motor for rotation is active.
*   `mMotorSpeed`: `-1` - The wheel is set to rotate at a speed of -1 (counter-clockwise).
*   `mMaxMotorTorque`: `100` - The maximum torque the motor can apply.

### Camera Bound Component

This component manages the visibility and loading of the entity based on camera distance.

*   `max_count`: `100` - Limits the number of these entities that can be active within the camera's view.
*   `distance`: `1000` - Defines the maximum distance from the camera at which the entity will be rendered.

### Damage Model Component

This component defines how the entity handles damage and its death behavior.

*   `hp`: `99999` - The entity has a very high health pool, making it difficult to destroy through normal means.
*   `fire_damage_amount`: `0.2` - The amount of damage taken from fire.
*   `materials_damage`: `1` - The entity can be damaged by contact with certain materials.
*   `blood_material`: `wood`, `ragdoll_material`: `wood` - Specifies the material associated with its "blood" and ragdoll, influencing interactions.
*   `air_needed`: `0`, `blood_multiplier`: `0`, `drop_items_on_death`: `0`, `falling_damages`: `0`, `fire_probability_of_ignition`: `0`, `critical_damage_resistance`: `1`, `is_on_fire`: `0`, `materials_create_messages`: `0`, `ragdoll_filenames_file`: `""`, `ui_report_damage`: `0` - These attributes indicate that the wheel does not require air, does not produce blood effects, does not drop items on death, is not affected by falling damage, has no chance of igniting, has high resistance to critical damage, is not initially on fire, does not create messages when materials interact, has no ragdoll files, and does not report damage to the UI.