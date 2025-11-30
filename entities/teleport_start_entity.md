---
title: Teleport Start Entity
category: entities
---

# Teleport Start Entity

This document describes the `teleport_start.xml` entity, which functions as a teleportation destination point in Noita.

## Core Functionality

The primary purpose of this entity is to act as a marker for a teleportation destination. When a player or other entity interacts with a corresponding `teleport_end` entity, they are transported to the coordinates defined by this `teleport_start` entity.

## Key Components and Attributes

### `UIInfoComponent`

This component defines the in-game name and tooltip for the entity.

*   **`name`**: `$teleport_mystery_back` - This is a localization key, likely displaying as "Mystery Teleport" or similar in-game.

### `TeleportComponent`

This is the core component that defines the teleportation destination.

*   **`target_x_is_absolute_position`**: `1` - Indicates that `target.x` is an absolute world coordinate.
*   **`target_y_is_absolute_position`**: `1` - Indicates that `target.y` is an absolute world coordinate.
*   **`target.x`**: `937` - The absolute X-coordinate of the teleportation destination.
*   **`target.y`**: `10` - The absolute Y-coordinate of the teleportation destination.

### `HitboxComponent`

Defines the collision area of the entity.

*   **`aabb_min_x`**: `-15`
*   **`aabb_min_y`**: `-15`
*   **`aabb_max_x`**: `15`
*   **`aabb_max_y`**: `15`
    These values define a square hitbox centered around the entity's origin.

### `LightComponent`

This entity has two `LightComponent` instances, creating a visual glow effect.

*   **`radius`**: `255` (for the first instance) and `64` (for the second) - Controls the size of the light emitted.
*   **`fade_out_time`**: `1.5` - The time in seconds for the light to fade out.
*   **`r`, `g`, `b`**: `64`, `100`, `255` - Defines the color of the light (a shade of blue).
*   **`offset_y`**: `-16` - Shifts the light source downwards relative to the entity's center.

### `SpriteParticleEmitterComponent`

This component generates visual particles to enhance the teleportation effect.

*   **`sprite_file`**: `data/particles/whirl_0$[1-8].png` - Specifies the sprite sheet used for the particles. The `$[1-8]` indicates a sequence of sprites.
*   **`lifetime`**: `1.5` - The duration each particle exists.
*   **`color.a`**: `0.75` - Initial transparency of the particles.
*   **`color_change.a`**: `-0.8` - The rate at which particles fade out.
*   **`angular_velocity`**: `7.5` - The speed at which particles rotate.
*   **`scale_velocity.x`, `scale_velocity.y`**: `1.0075` - The rate at which particles scale up over their lifetime.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2`, `4` - Controls the timing between particle emissions.
*   **`count_min`, `count_max`**: `1`, `1` - The number of particles emitted per emission event.
*   **`randomize_position`, `randomize_velocity`, `randomize_lifetime`, `randomize_angular_velocity`, `randomize_rotation`**: These attributes introduce variation in particle behavior, making the effect less uniform.

### `AudioLoopComponent`

Two `AudioLoopComponent` instances are present to play ambient sounds associated with the teleportation effect.

*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound events.
*   **`event_name`**: `misc/teleport_loop` and `misc/teleport_emitter_loop` - The specific sound events to be played.
*   **`auto_play`**: `1` - Ensures the sounds start playing automatically when the entity is active.