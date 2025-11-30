---
title: Base Torch Particle Emitter
category: entities
---

# Base Torch Particle Emitter

This entity defines the particle effects associated with a basic torch. It utilizes multiple `ParticleEmitterComponent` instances to generate smoke, sparks, and fire particles, creating a dynamic visual effect.

## Key Components

### ParticleEmitterComponent

This component is responsible for generating and controlling particles. The `base_torch_particle.xml` file uses four instances of this component to create different aspects of the torch's visual effect.

#### Common Attributes

*   **`_tags`**: Defines when the emitter is active. `enabled_in_world` and `enabled_in_hand` indicate it functions both in the game world and when held by the player. `fire` suggests it's related to fire effects.
*   **`emitted_material_name`**: Specifies the type of material the particles will be made from (e.g., "smoke", "spark", "fire").
*   **`offset.x`, `offset.y`**: The base position from which particles are emitted relative to the entity's origin.
*   **`x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`**: Defines the random range for the particle's initial position offset.
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: Sets the initial velocity range for the emitted particles.
*   **`count_min`, `count_max`**: The minimum and maximum number of particles emitted per emission event.
*   **`lifetime_min`, `lifetime_max`**: The minimum and maximum duration (in seconds) each particle will exist.
*   **`create_real_particles`**: If set to "1", these particles will interact with the game world as physical entities.
*   **`emit_cosmetic_particles`**: If set to "0", these particles are not considered cosmetic and may have gameplay implications.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The minimum and maximum number of frames between particle emission events.
*   **`is_emitting`**: If set to "1", the emitter is active.

#### Specific Attributes

*   **`custom_style="FIRE"`**: (Used for "spark" emitter) Applies a specific visual style, likely related to fire effects.
*   **`fire_cells_dont_ignite_damagemodel="1"`**: (Used for "fire" emitter) Prevents the emitted fire particles from igniting damage models, which might be desirable for a contained torch effect.

### Emitter Configurations

The entity uses four `ParticleEmitterComponent` instances:

1.  **Smoke Emitter**:
    *   `emitted_material_name="smoke"`
    *   Emits a moderate number of particles with a slight upward velocity.
    *   `emission_interval_min_frames="60"`, `emission_interval_max_frames="250"`: Relatively infrequent emission.

2.  **Spark Emitter 1**:
    *   `emitted_material_name="spark"`
    *   `custom_style="FIRE"`
    *   Emits a small cluster of sparks with a strong upward velocity.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="3"`: Very frequent emission, creating a constant stream of sparks.

3.  **Spark Emitter 2**:
    *   `emitted_material_name="spark"`
    *   Similar to Spark Emitter 1 but with a slightly smaller emission count and a slightly less frequent emission interval.

4.  **Fire Emitter**:
    *   `emitted_material_name="fire"`
    *   Emits a small number of fire particles with a strong upward velocity.
    *   `fire_cells_dont_ignite_damagemodel="1"`: Prevents these fire particles from igniting other entities.
    *   `emission_interval_min_frames="2"`, `emission_interval_max_frames="6"`: Frequent emission.