---
title: Teleportation Blast Particle
category: entities/particles
---

---

# Teleportation Blast Particle

This entity defines the visual and light effects for a teleportation blast in Noita. It utilizes a `SpriteParticleEmitterComponent` to generate particles and a `LightComponent` to add a glow effect.

## SpriteParticleEmitterComponent

This component controls the emission of particles that form the visual blast.

### Key Attributes:

*   **`sprite_file`**: Specifies the sprite definition for the individual particles.
    *   `data/particles/teleparticle.xml`
*   **`lifetime`**: The duration each particle exists.
    *   `0.4` seconds
*   **`scale.x`, `scale.y`**: Initial scale of the particles.
    *   `scale.x="1"`, `scale.y="0.2"` (particles are wider than they are tall)
*   **`color_change.a`**: How the alpha (transparency) of the particle changes over its lifetime.
    *   `-0.2` (particles fade out)
*   **`scale_velocity.x`, `scale_velocity.y`**: How the scale of the particles changes over their lifetime.
    *   `scale_velocity.x="-0.2"` (particles shrink horizontally)
    *   `scale_velocity.y="1"` (particles grow vertically)
*   **`randomize_velocity.min_y`, `randomize_velocity.max_y`**: The range of vertical velocity applied to emitted particles.
    *   `randomize_velocity.min_y="-40"`
    *   `randomize_velocity.max_y="40"`
*   **`randomize_position.min_x`, `randomize_position.max_x`**: The range of horizontal position offset for emitted particles.
    *   `randomize_position.min_x="-5"`
    *   `randomize_position.max_x="5"`
*   **`randomize_position.min_y`, `randomize_position.max_y`**: The range of vertical position offset for emitted particles.
    *   `randomize_position.min_y="-5"`
    *   `randomize_position.max_y="5"`
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: The time between particle emissions.
    *   `emission_interval_min_frames="3"`
    *   `emission_interval_max_frames="6"`
*   **`count_min`, `count_max`**: The number of particles emitted per interval.
    *   `count_min="1"`
    *   `count_max="1"`

## LightComponent

This component adds a dynamic light source to the entity.

### Key Attributes:

*   **`_enabled`**: Whether the light component is active.
    *   `1` (enabled)
*   **`radius`**: The radius of the light's influence.
    *   `60`
*   **`r`, `g`, `b`**: The RGB color values of the light.
    *   `r="80"`
    *   `g="60"`
    *   `b="0"` (This creates a yellowish-orange light)