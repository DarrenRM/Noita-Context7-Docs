---
title: Ocarina Projectile (A2)
category: entities
---

# Ocarina Projectile (A2)

This document details the configuration for the "Ocarina A2" projectile entity in Noita, primarily used for its musical properties.

## Entity Definition

The core entity is a player projectile with specific behaviors and visual/audio components.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
	<!-- ... other components ... -->
</Entity>
```

## Key Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component defines fundamental projectile physics.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `gravity_y`      | `0`     | No vertical gravity applied to this projectile. |
| `air_friction`   | `8`     | Moderate air resistance.                        |
| `mass`           | `0.01`  | Very low mass, making it light and fast.        |

### Projectile Behavior (`ProjectileComponent`)

This component governs the projectile's movement, lifespan, and interaction properties.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | `0.5`, `0.7` | Controls the arc of the projectile.                                         |
| `speed_min`, `speed_max`  | `250`, `450` | Defines the range of initial projectile speeds.                             |
| `lifetime`                | `2`     | The projectile exists for a maximum of 2 seconds.                           |
| `damage`                  | `0`     | This projectile does not deal direct damage.                                |
| `on_collision_die`        | `0`     | The projectile does not die upon collision.                                 |
| `lifetime_randomness`     | `0`     | Lifespan is consistent, not randomized.                                     |
| `knockback_force`         | `0.001` | Minimal knockback effect on collision.                                      |

### Particle Emitter (`ParticleEmitterComponent`)

Generates white sparks as a visual effect.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `emitted_material_name` | `spark_white` | The material used for the emitted particles.                                |
| `count_min`, `count_max`  | `8`, `10` | Emits 8 to 10 particles per emission.                                       |
| `lifetime_min`, `lifetime_max` | `0.2`, `1.2` | Particles last between 0.2 and 1.2 seconds.                                 |
| `is_trail`            | `0`     | Particles are not emitted as a continuous trail.                            |
| `airflow_force`       | `1.5`   | Particles are affected by airflow.                                          |
| `create_real_particles` | `0`     | These are cosmetic particles, not physical entities.                        |

### Sprite Particle Emitter (`SpriteParticleEmitterComponent`)

Emits "note" sprites for a musical visual effect.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `sprite_file`             | `data/particles/note_$[1-4].xml` | Uses one of four note sprite variations.                                    |
| `lifetime`                | `1.5`   | Sprites persist for 1.5 seconds.                                            |
| `color.r`, `color.g`, `color.b`, `color.a` | `0.4`, `1`, `1`, `1` | Initial color is a bright cyan.                                             |
| `color_change.a`          | `-1`    | Alpha (transparency) decreases over the sprite's lifetime.                  |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `4`, `6` | Sprites are emitted every 4 to 6 frames.                                    |
| `count_min`, `count_max`  | `1`, `1` | Emits one sprite per emission.                                              |
| `randomize_rotation.min`, `randomize_rotation.max` | `-0.3415`, `0.3415` | Sprites have a random initial rotation.                                     |
| `entity_velocity_multiplier` | `0.1` | Sprites inherit a small portion of the projectile's velocity.               |

### Variable Storage (`VariableStorageComponent`)

Stores the specific note identifier.

| Attribute     | Value   | Description                                     |
| :------------ | :------ | :---------------------------------------------- |
| `name`        | `ocarina_note` | The variable name.                              |
| `value_string` | `a2`    | The value, indicating this is the "A2" note.    |

### Lua Component (`LuaComponent`)

Executes Lua script upon entity addition.

| Attribute             | Value                           | Description                                                                 |
| :-------------------- | :------------------------------ | :-------------------------------------------------------------------------- |
| `script_source_file`  | `data/scripts/magic/ocarina.lua` | The script responsible for the ocarina's magical effects.                   |
| `execute_on_added`    | `1`                             | The script runs immediately when the projectile is created.                 |
| `remove_after_executed` | `1`                             | The Lua component is removed after its script has run once.                 |

### Audio Component (`AudioComponent`)

Plays the sound effect for the "A2" ocarina note.

| Attribute        | Value                                | Description                                     |
| :--------------- | :----------------------------------- | :---------------------------------------------- |
| `file`           | `data/audio/Desktop/projectiles.bank` | The audio bank containing the sound.            |
| `event_root`     | `player_projectiles/ocarina/a2`      | The specific sound event to trigger.            |
| `set_latest_event_position` | `1` | The sound will be positioned at the projectile's location. |