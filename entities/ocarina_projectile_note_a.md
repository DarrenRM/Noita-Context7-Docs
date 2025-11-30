---
title: Ocarina Projectile (Note A)
category: entities
---

```

# Ocarina Projectile (Note A)

This document details the configuration for the "Ocarina A" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is based on the `base_projectile.xml` and is tagged as `projectile_player`.

### Base Projectile Attributes

*   **`gravity_y`**: `0` - The projectile is not affected by gravity.
*   **`air_friction`**: `8` - Moderate air resistance.
*   **`mass`**: `0.01` - Very light mass.

### Projectile Component

This component defines the projectile's behavior and trajectory.

*   **`_enabled`**: `1` - The component is active.
*   **`lob_min` / `lob_max`**: `0.5` / `0.7` - Controls the arc of the projectile.
*   **`speed_min` / `speed_max`**: `250` / `450` - Defines the projectile's speed range.
*   **`direction_random_rad`**: `0.00` - No randomness in initial direction.
*   **`lifetime`**: `2` - The projectile exists for 2 seconds.
*   **`damage`**: `0` - The projectile itself deals no damage.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.
*   **`on_death_explode`**: `0` - The projectile does not explode when it dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime ends.

### Particle Emitters

This projectile utilizes two particle emitters to create visual effects.

#### `ParticleEmitterComponent` (Spark Effect)

*   **`emitted_material_name`**: `spark_white` - Emits white sparks.
*   **`count_min` / `count_max`**: `8` / `10` - Emits 8 to 10 particles per emission.
*   **`lifetime_min` / `lifetime_max`**: `0.2` / `1.2` - Particles last between 0.2 and 1.2 seconds.
*   **`x_vel_min` / `x_vel_max`**: `0` / `80` - Horizontal velocity range for particles.
*   **`y_vel_min` / `y_vel_max`**: `-10` / `10` - Vertical velocity range for particles.
*   **`airflow_force`**: `1.5` - Particles are affected by airflow.

#### `SpriteParticleEmitterComponent` (Note Effect)

*   **`sprite_file`**: `data/particles/note_$[1-4].xml` - Uses note sprites (likely variations 1-4).
*   **`lifetime`**: `1.5` - These sprites last for 1.5 seconds.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `4` / `6` - Sprites are emitted every 4 to 6 frames.
*   **`count_min` / `count_max`**: `1` / `1` - Emits one sprite at a time.
*   **`randomize_rotation`**: `min="-0.3415" max="0.3415"` - Sprites have randomized rotation.
*   **`entity_velocity_multiplier`**: `0.1` - Sprites inherit a small portion of the projectile's velocity.

## Scripting and Audio

### `VariableStorageComponent`

*   **`name`**: `ocarina_note`
*   **`value_string`**: `a` - This variable likely identifies the specific ocarina note.

### `LuaComponent`

*   **`script_source_file`**: `data/scripts/magic/ocarina.lua` - Links to the script that handles ocarina logic.
*   **`execute_on_added`**: `1` - The script executes immediately when the projectile is added.
*   **`remove_after_executed`**: `1` - The script component is removed after execution.

### `AudioComponent`

*   **`file`**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank.
*   **`event_root`**: `player_projectiles/ocarina/a` - Defines the specific audio event for this projectile.