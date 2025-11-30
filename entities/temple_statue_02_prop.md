---
title: Temple Statue 02 Prop
category: entities
---

# Temple Statue 02 Prop

This document describes the `temple_statue_02.xml` entity, a prop found in the game Noita. It's a static object with physical properties and a health component.

## Key Components

### PhysicsBody2Component
This component defines the physical behavior of the statue.

*   **angular_damping**: `0.1` - Controls how quickly rotational velocity decreases.
*   **init_offset_x**: `11` - Initial horizontal offset for the physics body.
*   **init_offset_y**: `29` - Initial vertical offset for the physics body.
*   **root_offset_x**: `8` - Horizontal offset for the root of the physics body.
*   **root_offset_y**: `8` - Vertical offset for the root of the physics body.

### PhysicsImageShapeComponent
This component links the visual representation (image) to the physics body.

*   **image_file**: `data/props_gfx/temple_statue_02.png` - The sprite file used for the statue.
*   **is_root**: `1` - Indicates this is the primary visual element.
*   **centered**: `0` - The image is not centered on its origin.
*   **material**: `rock_box2d_hard` - The material type, influencing physics interactions.
*   **offset_x**: `0` - Horizontal offset of the image relative to the physics body.
*   **offset_y**: `0` - Vertical offset of the image relative to the physics body.

### DamageModelComponent
This component defines how the statue takes damage and what happens upon destruction.

*   **air_needed**: `0` - Does not require air to function or take damage.
*   **blood_material**: `sand` - The material that appears when damaged.
*   **drop_items_on_death**: `0` - No items are dropped when destroyed.
*   **falling_damages**: `0` - Does not take damage from falling.
*   **fire_damage_amount**: `0` - Does not take fire damage.
*   **fire_probability_of_ignition**: `0` - Cannot ignite from fire.
*   **critical_damage_resistance**: `0` - No resistance to critical damage.
*   **hp**: `1200` - The statue's health points.
*   **blood_multiplier**: `0.01` - Multiplier for blood material generation.
*   **is_on_fire**: `0` - The statue does not start on fire.
*   **materials_create_messages**: `0` - No messages are generated when materials interact.
*   **materials_damage**: `0` - Does not take damage from material interactions.
*   **ui_force_report_damage**: `1` - Damage taken will be reported to the UI.
*   **ragdoll_filenames_file**: `""` - No ragdoll files are associated with its destruction.
*   **ragdoll_material**: `""` - No specific material for ragdoll physics.