---
title: Chaos Polymorph Field Projectile
category: entities
---

# Chaos Polymorph Field Projectile

This document details the configuration for the Chaos Polymorph Field projectile in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is defined by an `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" 
   >
  <!-- ... components ... -->
</Entity>
```

## Key Components

### GameAreaEffectComponent

This component defines the area of effect for the projectile.

| Attribute | Value | Description |
|---|---|---|
| `radius` | `28` | The radius of the area affected by the projectile. |

### ParticleEmitterComponent (x2)

These components are responsible for emitting visual particles to represent the projectile's effect. Both use `plasma_fading_pink` material.

**Emitter 1:**

| Attribute | Value | Description |
|---|---|---|
| `lifetime_min` | `0.5` | Minimum lifetime of emitted particles in seconds. |
| `lifetime_max` | `1.5` | Maximum lifetime of emitted particles in seconds. |
| `count_min` | `2` | Minimum number of particles emitted per burst. |
| `count_max` | `4` | Maximum number of particles emitted per burst. |
| `area_circle_radius.max` | `28` | Maximum radius for particle emission within the area. |
| `airflow_force` | `1.7` | Force applied to particles by airflow. |
| `emission_interval_min_frames` | `1` | Minimum frames between particle emissions. |
| `emission_interval_max_frames` | `1` | Maximum frames between particle emissions. |

**Emitter 2:**

| Attribute | Value | Description |
|---|---|---|
| `lifetime_min` | `0.5` | Minimum lifetime of emitted particles in seconds. |
| `lifetime_max` | `2.5` | Maximum lifetime of emitted particles in seconds. |
| `count_min` | `4` | Minimum number of particles emitted per burst. |
| `count_max` | `4` | Maximum number of particles emitted per burst. |
| `area_circle_radius.min` | `28` | Minimum radius for particle emission within the area. |
| `area_circle_radius.max` | `28` | Maximum radius for particle emission within the area. |
| `airflow_force` | `0.8` | Force applied to particles by airflow. |
| `emission_interval_min_frames` | `1` | Minimum frames between particle emissions. |
| `emission_interval_max_frames` | `1` | Maximum frames between particle emissions. |

### Base File Inclusion

The projectile inherits properties from `data/entities/projectiles/deck/base_field.xml`.

#### SpriteComponent

Defines the visual appearance of the projectile.

| Attribute | Value | Description |
|---|---|---|
| `image_file` | `data/projectiles_gfx/blast_polymorph.xml` | Path to the sprite image file. |

#### SpriteParticleEmitterComponent

Emits additional cosmetic particles for visual flair.

| Attribute | Value | Description |
|---|---|---|
| `sprite_file` | `data/particles/shine_03.xml` | Path to the sprite file for these particles. |
| `lifetime` | `2` | Lifetime of these particles in seconds. |
| `color.r`, `color.g`, `color.b`, `color.a` | `1` | Initial color of the particles (white). |
| `color_change.a` | `-1` | Alpha value decreases over the particle's lifetime. |
| `randomize_rotation.min`, `randomize_rotation.max` | `-3.1415` to `3.1415` | Random initial rotation. |
| `randomize_angular_velocity.min`, `randomize_angular_velocity.max` | `-15` to `15` | Random angular velocity. |

#### ProjectileComponent

Defines the projectile's behavior and effects.

| Attribute | Value | Description |
|---|---|---|
| `damage_game_effect_entities` | `data/entities/misc/effect_polymorph_random.xml,` | Entity applied when the projectile hits, causing a random polymorph effect. |
| `friendly_fire` | `0` | Projectile does not harm allies. |

##### config_explosion

Specifies the visual effect upon explosion.

| Attribute | Value | Description |
|---|---|---|
| `explosion_sprite` | `data/particles/blast_out_polymorph.xml` | Path to the sprite used for the explosion effect. |

#### AudioLoopComponent

Handles the looping sound effect for the projectile.

| Attribute | Value | Description |
|---|---|---|
| `file` | `data/audio/Desktop/projectiles.bank` | Audio bank containing the sound event. |
| `event_name` | `player_projectiles/field_transmutation/loop` | Name of the sound event to play. |
| `auto_play` | `1` | Sound plays automatically when the projectile is active. |