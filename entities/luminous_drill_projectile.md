---
title: Luminous Drill Projectile
category: entities
---

# Luminous Drill Projectile

This document details the configuration of the "Luminous Drill" projectile in Noita, focusing on its core attributes and particle effects for AI-assisted modding.

## Core Projectile Attributes

The `ProjectileComponent` defines the fundamental behavior of the luminous drill.

### Key Attributes:

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the projectile's arc. Values closer to 1 indicate a straighter trajectory. |
| `speed_min`, `speed_max`  | `1400`  | The projectile's initial velocity.                                          |
| `friction`                | `0.0`   | How much the projectile's speed is reduced over time. `0.0` means no friction. |
| `on_collision_die`        | `1`     | The projectile is destroyed upon hitting a surface.                         |
| `lifetime`                | `2`     | The duration in seconds before the projectile is destroyed if it doesn't hit anything. |
| `damage`                  | `0.4`   | The amount of damage dealt by the projectile.                               |
| `ground_penetration_coeff`| `4`     | How effectively the projectile penetrates ground. Higher values mean better penetration. |
| `ground_penetration_max_durability_to_destroy` | `14` | The maximum durability of ground that can be destroyed by this projectile. |

## Particle Effects

The `ParticleEmitterComponent` elements define the visual trails and cosmetic effects associated with the luminous drill.

### Trail Effects:

*   **`emitted_material_name`**: `spark_green` - The type of particle emitted.
*   **`count_min`, `count_max`**: Controls the number of particles emitted per burst.
*   **`lifetime_min`, `lifetime_max`**: Duration of individual particles.
*   **`create_real_particles`**: `0` - Indicates cosmetic particles, not physical ones.
*   **`emit_cosmetic_particles`**: `1` - Ensures particles are visible.
*   **`is_trail`**: `1` - Marks the emitter as contributing to a visual trail.
*   **`offset.x`, `offset.y`**: Position of the emitter relative to the projectile.

There are multiple `ParticleEmitterComponent` instances, creating a dense and continuous green spark trail. Some emitters have longer particle lifetimes (`0.15` to `0.32`) and `fade_based_on_lifetime="1"` and `draw_as_long="1"` for a more pronounced trailing effect.

## Audio

The `AudioComponent` links the projectile to its sound effects.

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/luminous_drill`

## Variable Storage

The `VariableStorageComponent` stores the projectile's own file path, useful for referencing within the game.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/luminous_drill.xml`