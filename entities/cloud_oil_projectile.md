---
title: Cloud Oil Projectile
category: entities
---

# Cloud Oil Projectile

This entity defines a projectile that emits oil and smoke particles, creating a cloud effect. It's designed to be a player projectile with no damage and a long lifetime.

## Key Components

### ProjectileComponent

This component defines the core behavior of the projectile.

| Attribute             | Value   | Description                                     |
| :-------------------- | :------ | :---------------------------------------------- |
| `_enabled`            | `1`     | Enables the projectile component.               |
| `lob_min`, `lob_max`  | `0.8`-`1.0` | Controls the lobbing behavior (minimal).        |
| `speed_min`, `speed_max` | `0`     | Projectile has no initial speed.                |
| `direction_random_rad`| `0.00`  | No random direction applied.                    |
| `on_death_explode`    | `0`     | Does not explode on death.                      |
| `on_death_gfx_leave_sprite` | `0` | Does not leave a sprite on death.               |
| `on_lifetime_out_explode` | `0` | Does not explode when lifetime ends.            |
| `explosion_dont_damage_shooter` | `1` | If it were to explode, it wouldn't damage the shooter. |
| `on_collision_die`    | `0`     | Does not die on collision.                      |
| `lifetime`            | `999`   | Very long lifetime.                             |
| `damage`              | `0`     | Deals no damage.                                |
| `damage_every_x_frames` | `10`  | Damage is applied every 10 frames (effectively none due to `damage=0`). |

### ParticleEmitterComponent (Multiple)

This entity utilizes several `ParticleEmitterComponent`s to generate different visual effects.

#### Oil Particle Emitter (Bottom Cloud)

*   **`emitted_material_name`**: `oil`
*   **`offset.y`**: `3`
*   **`count_min`**, **`count_max`**: `1`-`10`
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `3`-`3`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_bottom.png`
*   **`create_real_particles`**: `1`

#### Smoke Particle Emitter (Cosmetic)

*   **`emitted_material_name`**: `smoke`
*   **`x_pos_offset_min`**, **`x_pos_offset_max`**: `-1`-`1`
*   **`y_pos_offset_min`**, **`y_pos_offset_max`**: `-1`-`1`
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`**, **`lifetime_max`**: `0.2`-`0.5`
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `10`-`10`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud.png`
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`
*   **`is_emitting`**: `0` (This emitter is likely a template or for specific conditions not met here)

#### Smoke Particle Emitter (Real)

*   **`emitted_material_name`**: `smoke`
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`**, **`lifetime_max`**: `0.2`-`0.5`
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `1`-`10`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud.png`
*   **`create_real_particles`**: `1`
*   **`is_emitting`**: `0` (Similar to the cosmetic smoke emitter, likely for specific conditions)

#### Oil Particle Emitter (Outline 1)

*   **`emitted_material_name`**: `oil`
*   **`y_pos_offset_min`**, **`y_pos_offset_max`**: `7`-`7`
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`**, **`lifetime_max`**: `0.5`-`0.8`
*   **`airflow_force`**: `0.015`
*   **`airflow_scale`**: `0.01`
*   **`airflow_time`**: `0.1`
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `5`-`5`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_outline.png`
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`

#### Oil Particle Emitter (Outline 2)

*   **`emitted_material_name`**: `oil`
*   **`y_pos_offset_min`**, **`y_pos_offset_max`**: `7`-`7`
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`**, **`lifetime_max`**: `2.5`-`3.8`
*   **`airflow_force`**: `0.15`
*   **`airflow_scale`**: `0.1`
*   **`airflow_time`**: `0.1`
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `55`-`60`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_outline.png`
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`

### LifetimeComponent

*   **`lifetime`**: `600` - The projectile persists for a significant duration.

### AudioComponent

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/cloud` - Assigns specific audio events for this projectile.