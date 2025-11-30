---
title: Light Chest Entity
category: entities
---

# Light Chest Entity

This document describes the `chest_light.xml` entity, which represents a light-emitting chest in Noita. This entity is primarily used for visual effects and does not contain items itself.

## Key Components

### `UIInfoComponent`

This component defines the in-game name of the entity.

*   **`name`**: `$item_chest_light` - The internal identifier for the chest's name displayed in the UI.

### `PhysicsBodyComponent`

Defines the physical properties of the chest.

*   **`allow_sleep`**: `1` - Allows the physics body to sleep when not in motion, optimizing performance.
*   **`is_bullet`**: `1` - Indicates that this entity can interact with physics as a projectile or movable object.
*   **`auto_clean`**: `1` - The entity will be automatically cleaned up when it's no longer needed.
*   **`hax_fix_going_through_ground`**: `1` - A workaround to prevent the entity from falling through the ground.

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the chest.

*   **`image_file`**: `data/buildings_gfx/chest_light.png` - The sprite used for the chest.
*   **`material`**: `rock_box2d_nohit_hard` - The physics material applied to the chest, affecting its interaction with the environment.

### `LightComponent`

This component makes the chest emit light.

*   **`r`, `g`, `b`**: `255`, `255`, `255` - Sets the light color to white.
*   **`radius`**: `64` - The radius of the light emitted.
*   **`fade_out_time`**: `0.75` - The time it takes for the light to fade out.

### `LuaComponent`

This component links the entity to a Lua script for custom behavior.

*   **`script_source_file`**: `data/scripts/buildings/chest_light.lua` - The path to the Lua script that controls the chest's logic.
*   **`execute_every_n_frame`**: `5` - The script will execute every 5 frames.
*   **`_tags`**: `chest_disable` - This tag likely controls when the script is active or inactive.

### `ParticleEmitterComponent`

This component is responsible for emitting particles, likely for visual flair when the chest is active.

*   **`_enabled`**: `0` - The particle emitter is initially disabled.
*   **`_tags`**: `chest_enable` - This tag likely enables the particle emitter.
*   **`emitted_material_name`**: `plasma_fading` - The material of the particles being emitted.
*   **`count_min`, `count_max`**: `5`, `7` (and `1`, `1`) - Defines the range for the number of particles emitted per emission.
*   **`lifetime_min`, `lifetime_max`**: `10.1`, `20.3` - The duration particles exist.
*   **`is_emitting`**: `1` - The emitter is set to emit particles.