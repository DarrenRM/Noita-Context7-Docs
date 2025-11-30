---
title: Desert Teleport Building
category: entities
---

# Desert Teleport Building

This document describes the `teleport_desert.xml` entity, which represents a teleportation building found in the desert biome.

## Core Functionality

### `TeleportComponent`

This component defines the teleportation behavior of the building.

*   **`target_x_is_absolute_position`**: `1` (True) - The `target.x` value is an absolute world coordinate.
*   **`target_y_is_absolute_position`**: `1` (True) - The `target.y` value is an absolute world coordinate.
*   **`target.x`**: `7522` - The absolute X-coordinate of the teleportation destination.
*   **`target.y`**: `-133` - The absolute Y-coordinate of the teleportation destination.

## Visual and Audio Components

### `UIInfoComponent`

Provides basic information for UI display.

*   **`name`**: `$teleport_world` - The internal name for UI elements.

### `HitboxComponent`

Defines the physical boundaries of the building.

*   **`aabb_min_x`**: `-15` - Minimum X-axis extent of the bounding box.
*   **`aabb_min_y`**: `-15` - Minimum Y-axis extent of the bounding box.
*   **`aabb_max_x`**: `15` - Maximum X-axis extent of the bounding box.
*   **`aabb_max_y`**: `15` - Maximum Y-axis extent of the bounding box.

### `LightComponent`

These components add visual lighting effects to the building.

*   **First `LightComponent`**:
    *   `_enabled`: `1` (True)
    *   `radius`: `255`
    *   `fade_out_time`: `1.5`
    *   `r`, `g`, `b`: `64`, `100`, `255` (Blueish hue)
    *   `offset_y`: `-16`
*   **Second `LightComponent`**:
    *   `_enabled`: `1` (True)
    *   `radius`: `64`
    *   `fade_out_time`: `1.5`
    *   `r`, `g`, `b`: `64`, `100`, `255` (Blueish hue)
    *   `offset_y`: `-16`

### `SpriteParticleEmitterComponent`

Emits animated sprite particles to create a visual effect.

*   **`sprite_file`**: `data/particles/whirl_0$[1-8].png` - Uses a sequence of sprite files for animation.
*   **`lifetime`**: `1.5` - Duration of each particle.
*   **`color.a`**: `0.75` - Initial alpha transparency.
*   **`color_change.a`**: `-0.8` - Alpha decreases over the particle's lifetime.
*   **`angular_velocity`**: `7.5` - Speed of particle rotation.
*   **`scale_velocity.x`, `scale_velocity.y`**: `1.0075` - Particles slightly grow over time.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2` to `4` - Controls the rate of particle emission.
*   **`count_min`, `count_max`**: `1` - Emits one particle at a time.
*   **`randomize_position`**: Small random offsets for particle spawn points.
*   **`randomize_velocity`**: Random initial velocities for particles.
*   **`randomize_lifetime`**: Small variations in particle lifespan.
*   **`randomize_angular_velocity`**: Variations in particle rotation speed.
*   **`randomize_rotation`**: Variations in initial particle rotation.

### `ParticleEmitterComponent` (x2)

These components emit material particles for visual effects.

*   **First `ParticleEmitterComponent`**:
    *   **`emitted_material_name`**: `spark_blue` - The material of the emitted particles.
    *   **`lifetime_min`, `lifetime_max`**: `3` to `4` - Duration of emitted particles.
    *   **`count_min`, `count_max`**: `75` to `115` - Number of particles emitted per interval.
    *   **`area_circle_radius.min`, `area_circle_radius.max`**: `15` - Particles are emitted within a circular area.
    *   **`airflow_force`, `airflow_time`, `airflow_scale`**: Parameters for airflow influence on particles.
    *   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `12` - Fixed emission interval.
    *   **`velocity_always_away_from_center`**: `11` - Particles are pushed outwards from the emitter's center.
*   **Second `ParticleEmitterComponent`**:
    *   **`emitted_material_name`**: `spark_blue`
    *   **`lifetime_min`, `lifetime_max`**: `3` to `4`
    *   **`count_min`, `count_max`**: `1` - Emits a single particle at a time.
    *   **`area_circle_radius.min`, `area_circle_radius.max`**: `0` to `15` - Particles can be emitted from the center outwards.
    *   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `12`
    *   **`velocity_always_away_from_center`**: `0` - No specific outward velocity force.

### `AudioLoopComponent` (x2)

These components play looping audio effects.

*   **First `AudioLoopComponent`**:
    *   **`file`**: `data/audio/Desktop/misc.bank`
    *   **`event_name`**: `misc/teleport_loop`
    *   **`auto_play`**: `1` (True)
*   **Second `AudioLoopComponent`**:
    *   **`file`**: `data/audio/Desktop/misc.bank`
    *   **`event_name`**: `misc/teleport_emitter_loop`
    *   **`auto_play`**: `1` (True)