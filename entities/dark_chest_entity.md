---
title: Dark Chest Entity
category: entities
---

# Dark Chest Entity

This document describes the `chest_dark.xml` entity, which represents a dark chest in Noita. This entity is designed to be a container that can hold items and has specific visual and interactive properties.

## Key Components and Attributes

### `UIInfoComponent`

This component defines the user interface information for the chest.

*   **`name`**: `$item_chest_dark` - The internal name used for localization and referencing.

### `PhysicsBodyComponent`

Handles the physical properties of the chest in the game world.

*   **`_tags`**: `enabled_in_world`, `item_physics`, `chest` - Tags that define its behavior and interactions.
*   **`allow_sleep`**: `1` - Allows the physics body to sleep when not in motion to save performance.
*   **`is_bullet`**: `1` - Indicates it can be treated as a projectile or dynamic object.
*   **`auto_clean`**: `1` - The entity will be automatically cleaned up when it's no longer needed.
*   **`hax_fix_going_through_ground`**: `1` - A workaround to prevent the entity from falling through the ground.

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the chest.

*   **`image_file`**: `data/buildings_gfx/chest_dark.png` - The sprite used for the chest.
*   **`material`**: `rock_box2d_nohit_hard` - The physics material, affecting its interaction with other objects.

### `LightComponent`

Adds a light source emanating from the chest.

*   **`r`, `g`, `b`**: `255`, `255`, `255` - Sets the light color to white.
*   **`radius`**: `64` - The range of the light.
*   **`fade_out_time`**: `0.75` - How long it takes for the light to fade out.

### `LuaComponent`

Attaches a Lua script to the entity for custom logic.

*   **`script_source_file`**: `data/scripts/buildings/chest_dark.lua` - The path to the script that controls the chest's behavior.
*   **`execute_every_n_frame`**: `5` - The script will execute every 5 frames.
*   **`_tags`**: `chest_disable` - This tag might be used to conditionally disable certain behaviors.

### `ParticleEmitterComponent`

Responsible for emitting particles, likely for visual effects when the chest is interacted with or opened.

*   **`_enabled`**: `0` - The emitter is initially disabled.
*   **`_tags`**: `chest_enable` - This tag likely enables the particle emission under specific conditions.
*   **`emitted_material_name`**: `blood` - The material of the particles emitted.
*   **`offset.x`, `offset.y`**: `0`, `-5` - The position offset for particle emission relative to the chest's center.
*   **`x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`**: Defines the spread of emitted particles.
*   **`count_min`, `count_max`**: `1`, `1` - The number of particles emitted per emission.
*   **`lifetime_min`, `lifetime_max`**: `10.1`, `20.3` - The duration each particle exists.
*   **`emit_real_particles`**: `1` - Indicates that actual game particles are created.
*   **`is_emitting`**: `1` - The emitter is configured to emit particles.