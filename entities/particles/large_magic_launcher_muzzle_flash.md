---
title: Large Magic Launcher Muzzle Flash
category: entities/particles
---

---

# Large Magic Launcher Muzzle Flash

This entity defines the visual and particle effects for the muzzle flash of a large magic launcher in Noita. It utilizes a sprite animation and two particle emitters to create a dynamic and visually appealing effect.

## SpriteComponent

This component handles the primary visual representation of the muzzle flash.

### Key Attributes:

*   **`image_file`**: Specifies the sprite sheet used for the animation. It uses a pattern `muzzle_magic_launcher_large_0$[1-5].png` indicating 5 frames.
*   **`rect_animation`**: Defines the name of the animation sequence to use from the sprite sheet.
*   **`next_rect_animation`**: Similar to `rect_animation`, likely for controlling animation flow.
*   **`emissive`**: Set to `1`, meaning the sprite emits light.
*   **`additive`**: Set to `1`, indicating additive blending for the sprite, common for light effects.
*   **`kill_entity_after_finished`**: Set to `1`, meaning the entity (and its effects) will be removed once the sprite animation is complete.
*   **`offset_x`**, **`offset_y`**: Adjusts the position of the sprite relative to the entity's origin.

## ParticleEmitterComponent (Primary)

This emitter is responsible for the initial burst of sparks upon firing.

### Key Attributes:

*   **`emitted_material_name`**: `spark_green` - the type of particle to emit.
*   **`x_vel_min`**, **`x_vel_max`**, **`y_vel_min`**, **`y_vel_max`**: Define the velocity range for emitted particles, creating a outward burst.
*   **`count_min`**, **`count_max`**: The number of particles emitted per burst.
*   **`lifetime_min`**, **`lifetime_max`**: Very short lifetimes, indicating these are quick, transient sparks.
*   **`create_real_particles`**: Set to `0`, meaning these are cosmetic particles and don't interact with physics in the same way as "real" particles.
*   **`emit_cosmetic_particles`**: Set to `1`, confirming these are cosmetic.
*   **`is_emitting`**: Set to `1`, meaning the emitter is active.

## ParticleEmitterComponent (Secondary)

This emitter creates a more sustained trail of sparks with different properties.

### Key Attributes:

*   **`emitted_material_name`**: `spark_green` - same particle type as the primary emitter.
*   **`x_vel_min`**, **`x_vel_max`**, **`y_vel_min`**, **`y_vel_max`**: Define a different velocity range, likely for a more trailing effect.
*   **`count_min`**, **`count_max`**: A smaller number of particles per emission.
*   **`lifetime_min`**, **`lifetime_max`**: Longer lifetimes, creating a lingering effect.
*   **`fade_based_on_lifetime`**: Set to `1`, particles will fade out as their lifetime progresses.
*   **`render_on_grid`**: Set to `1`, particles are rendered on the game grid.
*   **`airflow_force`**, **`airflow_time`**, **`airflow_scale`**: These attributes suggest the particles are influenced by airflow, adding a subtle drift.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: Controls the timing between particle emissions, creating a staggered effect.
*   **`create_real_particles`**: Set to `0` (cosmetic).
*   **`emit_cosmetic_particles`**: Set to `1` (cosmetic).
*   **`is_emitting`**: Set to `1` (active).