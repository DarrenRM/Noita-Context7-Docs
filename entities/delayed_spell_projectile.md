---
title: Delayed Spell Projectile
category: entities
---

# Delayed Spell Projectile

This document details the configuration for a player-owned projectile entity in Noita, specifically designed for delayed spell effects.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag, with the name `$projectile_default` and tagged as `projectile_player`.

## Base Projectile Configuration

Inherits fundamental projectile properties from `data/entities/base_projectile.xml`.

### Velocity Component

*   **`gravity_y`**: `0` - The projectile is not affected by gravity.
*   **`mass`**: `0.04` - A small mass value.

## Projectile Component

This component governs the specific behaviors and attributes of the projectile.

### Key Attributes:

*   **`_enabled`**: `1` - The component is active.
*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the lobbing behavior, suggesting a relatively straight trajectory.
*   **`speed_min` / `speed_max`**: `26` - The projectile travels at a constant speed of 26 units.
*   **`direction_random_rad`**: `0` - No random deviation in projectile direction.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - If an explosion were to occur, it would not damage the shooter.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision with entities.
*   **`die_on_liquid_collision`**: `0` - The projectile does not die when colliding with liquids.
*   **`lifetime`**: `100` - The projectile exists for 100 frames.
*   **`damage`**: `0` - The projectile deals no direct damage.
*   **`camera_shake_when_shot`**: `5.0` - Triggers a camera shake of magnitude 5.0 when the projectile is fired.
*   **`penetrate_entities`**: `1` - The projectile can pass through multiple entities.
*   **`damage_every_x_frames`**: `25` - If damage were applied, it would occur every 25 frames.

### Configuration Explosion

*   **`<config_explosion />`**: An empty tag, indicating no specific explosion configuration is applied.

## Light Component

Adds a light source to the projectile.

*   **`_enabled`**: `1` - The light component is active.
*   **`radius`**: `20` - The radius of the light.
*   **`r`, `g`, `b`**: `30`, `90`, `30` - Defines a greenish light color.

## Particle Emitter Component

Generates cosmetic particles to enhance the visual effect of the projectile.

### Key Attributes:

*   **`emitted_material_name`**: `plasma_fading_green` - The material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`x_vel_min` / `x_vel_max`**: `-20` / `20` - Horizontal velocity range for particles.
*   **`y_vel_min` / `y_vel_max`**: `-20` / `20` - Vertical velocity range for particles.
*   **`count_min` / `count_max`**: `1` / `1` - Emits a single particle per emission.
*   **`lifetime_min` / `lifetime_max`**: `0.65` / `1.2` - Particle lifetime in seconds.
*   **`emit_real_particles`**: `0` - Emits cosmetic particles, not physics-simulated ones.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`airflow_force`**: `0.3` - Applies a slight airflow effect.
*   **`emit_cosmetic_particles`**: `1` - Explicitly enables cosmetic particle emission.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `2` - Particles are emitted frequently, every 1-2 frames.
*   **`area_circle_radius.max`**: `4` - Particles are emitted within a small circular area.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime progresses.
*   **`is_emitting`**: `1` - The particle emitter is active.

## Audio Component

Plays a sound effect when the projectile is fired.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/delayed_spell` - The specific sound event for this projectile.

## Audio Loop Component

Plays a looping sound effect while the projectile is active.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_name`**: `player_projectiles/delayed_spell/loop` - The specific looping sound event.
*   **`auto_play`**: `1` - The loop starts automatically when the projectile is created.