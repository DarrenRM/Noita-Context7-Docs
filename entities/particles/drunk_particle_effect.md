---
title: Drunk Particle Effect
category: entities/particles
---

# Drunk Particle Effect

This documentation describes the `drunk.xml` entity, which defines a particle effect used in Noita. This effect is likely intended to visually represent a "drunk" state or a similar disorienting visual phenomenon.

## SpriteParticleEmitterComponent

This component governs the behavior and appearance of the particles emitted.

### Key Attributes:

*   **`sprite_file`**: `data/particles/drunk.xml`
    *   Specifies the XML file that defines the particle's appearance and behavior.
*   **`lifetime`**: `1.5`
    *   The duration in seconds each particle will exist.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 1`
    *   The initial color of the particles (fully opaque white in this case).
*   **`color_change.a`**: `-0.5`
    *   The rate at which the alpha (transparency) of the particles changes over their lifetime. This value indicates the particles will fade out.
*   **`gravity.y`**: `10`
    *   The gravitational force applied to the particles along the Y-axis, causing them to fall.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`, `3`
    *   The minimum and maximum number of frames between particle emissions, creating a slightly irregular emission rate.
*   **`count_min`, `count_max`**: `1`, `1`
    *   The minimum and maximum number of particles emitted at each emission event.
*   **`randomize_rotation.min`, `randomize_rotation.max`**: `-0.1415`, `0.1415`
    *   Applies a random rotation to each emitted particle within this range.
*   **`randomize_position.min_x`, `randomize_position.max_x`**: `-5`, `5`
    *   Randomizes the X-position of emitted particles within this range relative to the emitter's origin.
*   **`randomize_position.min_y`, `randomize_position.max_y`**: `-12`, `-10`
    *   Randomizes the Y-position of emitted particles within this range relative to the emitter's origin.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`**: `-7`, `7`
    *   Applies a random velocity to emitted particles along the X-axis.
*   **`randomize_velocity.min_y`, `randomize_velocity.max_y`**: `-20`, `-10`
    *   Applies a random velocity to emitted particles along the Y-axis.

### Other Attributes:

*   **`delay`**: `0` - No initial delay before emission starts.
*   **`velocity.x`, `velocity.y`**: `0`, `0` - Base velocity of particles before randomization.
*   **`velocity_slowdown`**: `0` - Particles do not slow down over time.
*   **`rotation`**: `0` - Base rotation of particles.
*   **`angular_velocity`**: `0` - Particles do not have a constant angular velocity.
*   **`use_velocity_as_rotation`**: `0` - Particle rotation is not driven by its velocity.
*   **`scale.x`, `scale.y`**: `1`, `1` - Initial scale of particles.
*   **`scale_velocity.x`, `scale_velocity.y`**: `0`, `0` - Particles do not change scale over time.