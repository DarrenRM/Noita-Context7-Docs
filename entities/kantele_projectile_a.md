---
title: Kantele Projectile (A)
category: entities
---

# Kantele Projectile (A)

This document details the `kantele_a.xml` entity, representing one of the musical note projectiles fired by the Kantele wand.

## Core Entity

The base entity is `$projectile_default`, inheriting common projectile properties.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="0"
			air_friction="8"
			mass="0.01"
		>
		</VelocityComponent>
	</Base>
    ...
</Entity>
```

## Projectile Component

This component defines the projectile's behavior and physical properties.

| Attribute              | Value   | Description                                                                 |
| :--------------------- | :------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`   | 0.5-0.7 | Controls the arc of the projectile.                                         |
| `speed_min`, `speed_max` | 250-450 | The range of initial velocities for the projectile.                         |
| `lifetime`             | 2       | How long the projectile exists before expiring.                             |
| `damage`               | 0       | This projectile itself does not deal damage.                                |
| `on_collision_die`     | 0       | The projectile does not die upon collision.                                 |
| `explosion_dont_damage_shooter` | 0 | N/A (as `on_death_explode` is 0)                                            |
| `lifetime_randomness`  | 0       | Projectile lifetime is fixed.                                               |
| `knockback_force`      | 0.001   | Minimal knockback applied on hit.                                           |

## Particle Emitters

This projectile utilizes two particle emitters to create visual effects.

### `ParticleEmitterComponent` (Spark Effect)

Generates white sparks.

| Attribute              | Value   | Description                                                                 |
| :--------------------- | :------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`| `spark_white` | The material used for the emitted particles.                                |
| `count_min`, `count_max` | 8-10    | Number of particles emitted per interval.                                   |
| `lifetime_min`, `lifetime_max` | 0.2-1.2 | Duration each spark particle exists.                                        |
| `x_vel_min`, `x_vel_max` | 0-80    | Horizontal velocity range for sparks.                                       |
| `y_vel_min`, `y_vel_max` | -10-10  | Vertical velocity range for sparks.                                         |
| `airflow_force`        | 1.5     | How much airflow affects the sparks.                                        |

### `SpriteParticleEmitterComponent` (Note Effect)

Emits sprite particles resembling musical notes.

| Attribute              | Value   | Description                                                                 |
| :--------------------- | :------ | :-------------------------------------------------------------------------- |
| `sprite_file`          | `data/particles/note_$[1-4].xml` | Uses a set of note sprites.                                                 |
| `lifetime`             | 1.5     | Duration each note sprite exists.                                           |
| `emission_interval_min_frames`, `emission_interval_max_frames` | 4-6 | Controls the rate of sprite emission.                                       |
| `count_min`, `count_max` | 1       | One note sprite emitted per interval.                                       |
| `randomize_rotation`   | +/- 0.3415 | Randomizes the initial rotation of note sprites.                            |
| `randomize_angular_velocity` | +/- 0.1415 | Randomizes the rotation speed of note sprites.                              |
| `entity_velocity_multiplier` | 0.1 | Note sprites inherit a small portion of the projectile's velocity.          |

## Variable Storage

Stores the specific note type.

```xml
<VariableStorageComponent
	name="kantele_note"
	value_string="a"
>
</VariableStorageComponent>
```

## Lua Component

Links to the script that handles the projectile's logic.

```xml
<LuaComponent
	script_source_file="data/scripts/magic/kantele.lua"
	execute_on_added="1"
	remove_after_executed="1"
>
</LuaComponent>
```

## Audio Component

Defines the sound played when the projectile is fired.

```xml
<AudioComponent
	file="data/audio/Desktop/projectiles.bank"
	event_root="player_projectiles/kantele/a"
	set_latest_event_position="1" >
</AudioComponent>
```