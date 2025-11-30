---
title: Summon Portal Projectile
category: entities
---

# Summon Portal Projectile

This entity defines the behavior and appearance of the "Summon Portal" projectile in Noita. It's a projectile that creates a temporary portal, likely for teleportation or summoning purposes.

## Key Components

### Base Projectile Properties

*   **`Base file="data/entities/base_projectile.xml"`**: Inherits fundamental projectile mechanics.
    *   **`VelocityComponent`**:
        *   `gravity_y="0"`: The projectile is not affected by gravity.
        *   `air_friction="2"`: Moderate air resistance.

### Visuals and Effects

*   **`UIInfoComponent`**:
    *   `name="$teleport_strange_unstable"`: Likely used for internal identification or UI display.
*   **`LightComponent` (x2)**: Creates a glowing effect.
    *   The first component provides a larger, softer blue glow (`r="64"`, `g="100"`, `b="255"`, `radius="255"`).
    *   The second component adds a brighter, blinking white light (`r="255"`, `g="255"`, `b="255"`, `radius="64"`, `blinking_freq="0.3"`).
*   **`SpriteComponent`**:
    *   `image_file="data/buildings_gfx/teleport_center.xml"`: Uses a sprite associated with teleportation structures.
    *   `additive="1"`: The sprite is rendered additively, contributing to a glowing effect.

### Particle Emitters

This projectile utilizes multiple `ParticleEmitterComponent`s to create visual flair.

*   **Emitter 1 (Constant Aura)**:
    *   `emitted_material_name="spark_purple"`: Emits purple sparks.
    *   `lifetime_min="3"`, `lifetime_max="4"`: Short particle lifespan.
    *   `count_min="10"`, `count_max="80"`: Variable number of particles emitted.
    *   `area_circle_radius.min="15"`, `area_circle_radius.max="15"`: Particles originate from a small circular area.
    *   `velocity_always_away_from_center="11"`: Particles are pushed outwards from the center.
    *   `emission_interval_min_frames="12"`, `emission_interval_max_frames="12"`: Emits particles at a steady rate.
*   **Emitter 2 (Initial Burst)**:
    *   `emitted_material_name="spark_purple"`: Emits purple sparks.
    *   `lifetime_min="3"`, `lifetime_max="4"`: Short particle lifespan.
    *   `x_vel_min="-20"`, `x_vel_max="20"`, `y_vel_min="-20"`, `y_vel_max="20"`: Particles are emitted with some velocity.
    *   `count_min="1"`, `count_max="1"`: Emits a single particle per interval.
    *   `area_circle_radius.min="0"`, `area_circle_radius.max="6"`: Particles originate from a very small area.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: Emits particles very frequently.
*   **Emitter 3 (Delayed Discharge)**:
    *   `emitted_material_name="spark_purple"`: Emits purple sparks.
    *   `delay_frames="118"`: This emitter activates after a significant delay.
    *   `lifetime_min="3"`, `lifetime_max="12"`: Longer particle lifespan.
    *   `x_vel_min="-250"`, `x_vel_max="250"`, `y_vel_min="-250"`, `y_vel_max="250"`: Particles are emitted with high velocity, creating a strong outward burst.
    *   `count_min="40"`, `count_max="80"`: Emits a large number of particles.
    *   `area_circle_radius.min="6"`, `area_circle_radius.max="6"`: Particles originate from a small area.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: Emits particles rapidly once activated.

### Audio

*   **`AudioLoopComponent` (x2)**: Plays looping sounds associated with teleportation.
    *   `event_name="misc/teleport_loop"`
    *   `event_name="misc/teleport_emitter_loop"`
*   **`AudioComponent`**: Plays a projectile-specific sound on impact or expiration.
    *   `event_root="player_projectiles/fizzle"`

### Behavior

*   **`LifetimeComponent`**:
    *   `lifetime="120"`: The projectile exists for 120 frames.
*   **`LuaComponent` (x2)**: Executes custom Lua scripts to control behavior.
    *   `script_source_file="data/scripts/projectiles/summon_portal_vibrate.lua"`: Likely handles visual vibration or animation.
    *   `script_source_file="data/scripts/projectiles/summon_portal_position_check.lua"`: Likely responsible for checking conditions or determining portal placement.