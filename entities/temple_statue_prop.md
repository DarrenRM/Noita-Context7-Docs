---
title: Temple Statue Prop
category: entities
---

# Temple Statue Prop

This document describes the `temple_statue_01.xml` entity, a prop found in the game Noita. It is a static object with physical properties and a health component.

## Key Components and Attributes

### PhysicsBody2Component
This component defines the physical behavior of the statue.

*   `angular_damping`: Controls how quickly rotational movement slows down.
*   `init_offset_x`, `init_offset_y`: Initial positional offsets for the physics body.
*   `root_offset_x`, `root_offset_y`: Offsets relative to the entity's root for physics calculations.

### PhysicsImageShapeComponent
This component defines the visual shape and collision properties based on an image.

*   `image_file`: Specifies the graphical asset used for the statue (`data/props_gfx/temple_statue_01.png`).
*   `is_root`: Indicates this is the primary visual component.
*   `centered`: Determines if the image is centered on its origin.
*   `material`: The physical material type, influencing interactions (`rock_box2d_hard`).
*   `offset_x`, `offset_y`: Positional offsets for the image shape.

### DamageModelComponent
This component handles how the statue reacts to damage and its health.

*   `air_needed`: Whether air is required for damage effects (0 means no).
*   `blood_material`: The material that appears when damaged (e.g., `sand`).
*   `drop_items_on_death`: Whether items are dropped upon destruction (0 means no).
*   `falling_damages`: Whether the statue takes damage from falling (0 means no).
*   `fire_damage_amount`, `fire_probability_of_ignition`: Settings related to fire damage.
*   `hp`: The statue's health points (1200).
*   `blood_multiplier`: Affects the amount of blood material generated.
*   `ui_force_report_damage`: Forces damage to be reported in the UI.
*   `ragdoll_filenames_file`, `ragdoll_material`: Settings for ragdoll physics upon death (empty here, so no ragdoll).