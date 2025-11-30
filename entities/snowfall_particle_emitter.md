---
title: Snowfall Particle Emitter
category: entities
---

# Snowfall Particle Emitter

This entity defines a particle emitter that generates falling snow. It's a simple setup primarily controlled by the `ParticleEmitterComponent`.

## ParticleEmitterComponent

This component is responsible for the visual and physical properties of the emitted particles.

### Key Attributes:

*   **`emitted_material_name`**: Specifies the material of the particles to be emitted. In this case, it's `"snow"`.
*   **`x_pos_offset_min`**, **`x_pos_offset_max`**: Defines the horizontal range from the emitter's origin where particles can spawn. Here, it's a range of -256 to 0, meaning particles spawn to the left of the emitter.
*   **`y_pos_offset_min`**, **`y_pos_offset_max`**: Defines the vertical range from the emitter's origin where particles can spawn. Here, it's 0 to 0, meaning particles spawn at the same vertical level as the emitter.
*   **`x_vel_min`**, **`x_vel_max`**: Sets the minimum and maximum horizontal velocity for emitted particles. Both are 0, meaning no horizontal movement.
*   **`y_vel_min`**, **`y_vel_max`**: Sets the minimum and maximum vertical velocity for emitted particles. Both are 0, meaning no initial vertical movement.
*   **`count_min`**, **`count_max`**: Determines the number of particles emitted per emission cycle. Here, it's between 1 and 10.
*   **`lifetime_min`**, **`lifetime_max`**: Sets the duration (in seconds) each particle exists. Here, it's between 0.2 and 0.5 seconds.
*   **`airflow_force`**: Represents the force applied to the particles by airflow. A value of `10.0` suggests a noticeable downward drift.
*   **`is_trail`**: If set to `1`, particles will leave a trail.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: Controls the frame interval between particle emissions. Here, it's set to 1 frame, meaning continuous emission.
*   **`create_real_particles`**: If set to `1`, actual particles are created, not just visual effects.
*   **`is_emitting`**: If set to `1`, the emitter is active.