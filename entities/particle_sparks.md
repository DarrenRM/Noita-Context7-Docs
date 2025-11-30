---
title: Particle Sparks
category: entities
---

# Particle Sparks

This entity defines a basic particle effect that generates sparks. It inherits from `base_projectile.xml` and utilizes several components to control its behavior, appearance, and emission.

## Key Components and Attributes

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component provides fundamental projectile properties.

*   **`<VelocityComponent>`**:
    *   `gravity_y`: Controls the downward acceleration of the particle.
        *   `200`: A moderate gravitational pull.
    *   `air_friction`: Simulates air resistance.
        *   `8.7`: A relatively high friction value, causing particles to slow down.

### Projectile (`<ProjectileComponent>`)

Defines the specific projectile-like behavior of the sparks.

*   `_enabled`: Whether the component is active.
    *   `1`: Enabled.
*   `speed_min`, `speed_max`: The range of initial speeds for the sparks.
    *   `450`, `650`: Sparks are launched with significant velocity.
*   `die_on_low_velocity`: If the particle should be destroyed when its speed drops below a certain threshold.
    *   `0`: Sparks will not die solely due to low velocity.
*   `on_death_explode`, `on_death_gfx_leave_sprite`, `on_lifetime_out_explode`: Controls what happens when the particle dies (e.g., explosion, leaving a sprite).
    *   `0`: These effects are disabled for this particle.
*   `damage`: The damage dealt by the particle.
    *   `0.0`: Sparks do not deal damage.
*   `bounce_always`: Whether the particle should always bounce.
    *   `1`: Sparks will always bounce.
*   `bounces_left`: The maximum number of bounces allowed.
    *   `10`: Sparks can bounce multiple times.
*   `bounce_energy`: The energy retained after each bounce (0.0 to 1.0).
    *   `0.5`: Sparks lose half their energy on each bounce.
*   `on_collision_die`: Whether the particle dies upon collision.
    *   `0`: Sparks do not die on collision.
*   `collide_with_entities`: Whether the particle can collide with other entities.
    *   `0`: Sparks do not collide with entities.
*   `lifetime`: The duration in seconds before the particle is automatically destroyed.
    *   `15`: Sparks exist for a moderate duration.

### Light (`<LightComponent>`)

Adds a light source to the particle.

*   `_enabled`: Whether the light component is active.
    *   `1`: Enabled.
*   `radius`: The range of the light.
    *   `64`: A moderate light radius.
*   `r`, `g`, `b`: The RGB color values of the light.
    *   `255`, `230`, `120`: A warm, yellowish-white light.
*   `fade_out_time`: How long it takes for the light to fade out.
    *   `0.5`: The light fades out relatively quickly.

### Sprite Particle Emitter (`<SpriteParticleEmitterComponent>`)

This component is responsible for emitting other particles (the sparks themselves).

*   `sprite_file`: The XML file defining the appearance of the emitted particles.
    *   `data/particles/sparkly.xml`: References a separate definition for the spark's visual properties.
*   `delay`, `lifetime`: Emission delay and lifetime of the emitter itself.
    *   `0`, `0`: The emitter is active immediately and has no inherent lifetime.
*   `color.r`, `color.g`, `color.b`, `color.a`: The initial color and alpha of the emitted particles.
    *   `1`, `1`, `1`, `0.8`: White with high opacity.
*   `color_change.r`, `color_change.g`, `color_change.b`, `color_change.a`: How the color changes over the particle's lifetime.
    *   `0`, `0`, `0`, `0`: No color change.
*   `velocity.x`, `velocity.y`: The base velocity applied to emitted particles.
    *   `0`, `0`: No base velocity.
*   `gravity.x`, `gravity.y`: The gravity applied to emitted particles.
    *   `0`, `-15`: A slight upward gravity, counteracting the main projectile's gravity.
*   `velocity_slowdown`: How much velocity is reduced each frame.
    *   `0`: No velocity slowdown.
*   `rotation`, `angular_velocity`: Rotation properties.
    *   `0`, `0`: No rotation.
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y`: Random variations in velocity.
    *   `min_x="-10"`, `max_x="10"`: Horizontal spread.
    *   `min_y="-30"`, `max_y="10"`: Vertical spread, with a tendency to move upwards.
*   `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`: Random variations in emission position.
    *   `min_x="-4"`, `max_x="4"`, `min_y="-4"`, `max_y="4"`: Small positional spread around the emitter.
*   `scale.x`, `scale.y`: Initial scale of the emitted particles.
    *   `1`, `1`: Standard size.
*   `scale_velocity.x`, `scale_velocity.y`: How the scale changes over time.
    *   `0`, `0`: No scale change.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: The frame range between emissions.
    *   `2`, `4`: Sparks are emitted frequently.
*   `count_min`, `count_max`: The number of particles emitted per interval.
    *   `1`, `2`: A small number of sparks are emitted at a time.