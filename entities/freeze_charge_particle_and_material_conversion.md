---
title: Freeze Charge Particle and Material Conversion
category: entities
---

# Freeze Charge Particle and Material Conversion

This entity defines the visual particles and material conversion effects associated with the "freeze charge" in Noita. It primarily utilizes particle emitters to create visual snow-like effects and a `MagicConvertMaterialComponent` to transform various liquids into their frozen counterparts.

## Key Components and Attributes

### SpriteParticleEmitterComponent

This component is responsible for emitting sprite-based particles, likely representing snowflakes.

*   **`sprite_file`**: Specifies the sprite to be used for the particles. In this case, it's a pattern that selects between `snowflake_1.xml` and `snowflake_2.xml`.
*   **`lifetime`**: The duration each particle exists (10 frames).
*   **`color`**: Initial color of the particles (white).
*   **`color_change`**: How the color changes over the particle's lifetime. Here, the alpha decreases, causing fading.
*   **`gravity`**: The gravitational pull on the particles (y-axis).
*   **`velocity_slowdown`**: How quickly particles lose velocity.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Controls the timing between particle emissions.
*   **`count_min`, `count_max`**: The number of particles emitted per interval.
*   **`randomize_rotation`**: Introduces random initial rotation to particles.
*   **`randomize_angular_velocity`**: Introduces random rotation speed.
*   **`randomize_position`**: Offsets the emission position within a small radius.
*   **`randomize_velocity`**: Adds random velocity components to emitted particles.

### ParticleEmitterComponent (x2)

These components emit simpler, non-sprite particles, likely for a more diffuse snow effect.

**First `ParticleEmitterComponent`:**

*   **`emitted_material_name`**: The material of the particles being emitted ("snow").
*   **`friction`**: How much friction affects particle movement.
*   **`gravity`**: Gravitational pull on these particles.
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: Defines the range of initial velocities.
*   **`count_min`, `count_max`**: Number of particles emitted.
*   **`fade_based_on_lifetime`**: Enables fading as particles age.
*   **`lifetime_min`, `lifetime_max`**: Duration of these particles.
*   **`emit_cosmetic_particles`**: Indicates these are visual-only particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Controls emission timing.
*   **`is_emitting`**: Whether the emitter is active.

**Second `ParticleEmitterComponent`:**

*   **`emitted_material_name`**: "snow".
*   **`offset`**: Offset of this emitter relative to the entity's origin.
*   **`x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`**: Defines the emission area.
*   **`gravity`**: Gravitational pull.
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: Initial velocity ranges.
*   **`count_min`, `count_max`**: Number of particles.
*   **`lifetime_min`, `lifetime_max`**: Duration of these particles (very short).
*   **`emit_cosmetic_particles`**: These are not cosmetic.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Emission timing.
*   **`emitter_lifetime_frames`**: How long this specific emitter remains active.

### MagicConvertMaterialComponent (x2)

These components handle the core functionality of freezing liquids.

**First `MagicConvertMaterialComponent`:**

*   **`stain_frozen`**: Marks the resulting material as "frozen" for other game mechanics.
*   **`from_material`**: The specific material to convert ("water").
*   **`to_material`**: The material it converts into ("ice_static").
*   **`steps_per_frame`**: How many conversion steps occur per game frame.
*   **`loop`**: Whether the conversion effect repeats.
*   **`is_circle`**: The conversion area is circular.
*   **`radius`**: The radius of the conversion effect.

**Second `MagicConvertMaterialComponent`:**

*   **`from_material_array`**: A comma-separated list of various liquid materials to be converted.
*   **`to_material_array`**: A corresponding list of frozen materials to convert into. This allows for a wide range of liquids to be frozen into their appropriate static ice forms (e.g., "water\_ice" to "ice\_static", "lava" to "rock\_static", "radioactive\_liquid" to "ice\_radioactive\_static").
*   **`steps_per_frame`**: Conversion steps per frame.
*   **`loop`**: Whether the conversion effect repeats.
*   **`is_circle`**: The conversion area is circular.
*   **`radius`**: The radius of the conversion effect.