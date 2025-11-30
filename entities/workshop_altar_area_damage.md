---
title: Workshop Altar Area Damage
category: entities
---

# Workshop Altar Area Damage

This entity defines an area that deals damage over time, likely intended for environmental hazards or special effects within the game.

## Key Components

### `LifetimeComponent`

Controls how long the entity exists.

*   **`lifetime`**: The base duration in frames the entity will persist.
*   **`randomize_lifetime.min`**: Minimum additional random lifetime.
*   **`randomize_lifetime.max`**: Maximum additional random lifetime.

### `AreaDamageComponent`

Defines the area that inflicts damage and its properties.

*   **`aabb_min.x`, `aabb_min.y`**: The minimum X and Y coordinates defining the bounding box of the damage area.
*   **`aabb_max.x`, `aabb_max.y`**: The maximum X and Y coordinates defining the bounding box of the damage area.
*   **`damage_per_frame`**: The amount of damage dealt to entities within the area each frame.
*   **`update_every_n_frame`**: How often the damage is applied (e.g., `10` means every 10 frames).
*   **`death_cause`**: A localization string defining the cause of death for entities killed by this area.
*   **`damage_type`**: The type of damage dealt (e.g., `DAMAGE_CURSE`).

### `ParticleEmitterComponent`

Responsible for generating visual effects (particles) within the area.

*   **`emitted_material_name`**: The material/type of particle to emit (e.g., `spark_red`).
*   **`x_pos_offset_min`, `x_pos_offset_max`**: The range of horizontal offsets for particle emission relative to the entity's position.
*   **`y_pos_offset_min`, `y_pos_offset_max`**: The range of vertical offsets for particle emission relative to the entity's position.
*   **`x_vel_min`, `x_vel_max`**: The minimum and maximum horizontal velocity of emitted particles.
*   **`y_vel_min`, `y_vel_max`**: The minimum and maximum vertical velocity of emitted particles.
*   **`gravity.y`**: The gravitational effect on the particles' vertical movement.
*   **`lifetime_min`, `lifetime_max`**: The minimum and maximum duration particles will exist.
*   **`count_min`, `count_max`**: The minimum and maximum number of particles emitted per emission event.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The range of frames between particle emission events.
*   **`emit_cosmetic_particles`**: Whether to emit particles that are purely visual.
*   **`is_emitting`**: A flag to enable/disable particle emission.

### `CameraBoundComponent`

Manages the entity's visibility and behavior relative to the camera.

*   **`max_count`**: The maximum number of this entity that can be active within the camera's view.
*   **`distance`**: The maximum distance from the camera at which the entity can be rendered or active.