---
title: Laser Lasergun Projectile
category: entities
---

# Laser Lasergun Projectile

This document details the configuration of the `laser_lasergun.xml` projectile entity in Noita, focusing on its key attributes for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag, which inherits base projectile properties from `data/entities/base_projectile.xml`.

```xml
<Entity name="$projectile_default">
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="0"
			air_friction="-2.0"
			mass="0.05"
			>
		</VelocityComponent>
	</Base>
    <!-- ... other components ... -->
</Entity>
```

## Projectile Component

This component governs the projectile's behavior, including its speed, trajectory, collision effects, and damage.

### Key Attributes:

| Attribute                 | Description                                                                 | Example Value |
| :------------------------ | :-------------------------------------------------------------------------- | :------------ |
| `lob_min`, `lob_max`      | Controls the minimum and maximum lobbing angle (deviation from straight).   | `0.8`, `1.1`  |
| `speed_min`, `speed_max`  | Defines the range of projectile speed.                                      | `1450`, `1850`|
| `direction_random_rad`    | Adds a small random deviation to the projectile's direction in radians.     | `0.003`       |
| `on_death_explode`        | If `1`, the projectile explodes upon death.                                 | `1`           |
| `on_lifetime_out_explode` | If `1`, the projectile explodes when its lifetime expires.                  | `1`           |
| `explosion_dont_damage_shooter` | If `1`, the explosion will not damage the entity that shot it.            | `1`           |
| `on_collision_die`        | If `1`, the projectile dies upon colliding with something.                  | `1`           |
| `die_on_liquid_collision` | If `1`, the projectile dies upon colliding with a liquid.                   | `1`           |
| `lifetime`                | The duration in seconds before the projectile expires.                      | `20`          |
| `velocity_sets_scale`     | If `1`, the projectile's velocity is scaled by its speed.                   | `1`           |
| `velocity_sets_scale_coeff` | Coefficient for scaling velocity.                                           | `2`           |
| `camera_shake_when_shot`  | The intensity of camera shake when this projectile is fired.                | `2.0`         |
| `damage`                  | The base damage dealt by the projectile.                                    | `1`           |
| `knockback_force`         | The force applied to entities upon impact.                                  | `3.0`         |

### `config_explosion` Sub-element:

This nested element defines the properties of the explosion that occurs when `on_death_explode` or `on_lifetime_out_explode` is triggered.

| Attribute                 | Description                                                                 | Example Value |
| :------------------------ | :-------------------------------------------------------------------------- | :------------ |
| `camera_shake`            | Intensity of camera shake during the explosion.                             | `1.5`         |
| `explosion_radius`        | The radius of the explosion effect.                                         | `3`           |
| `explosion_sprite`        | Path to the sprite used for the explosion visual.                           | `data/particles/explosion_016_plasma_pink.xml` |
| `create_cell_material`    | Material created by the explosion (e.g., for creating new liquids/cells).   | `plasma_fading` |
| `create_cell_probability` | Probability of creating a new cell material.                                | `15`          |
| `hole_enabled`            | If `1`, the explosion creates holes in surfaces.                            | `1`           |
| `ray_energy`              | The energy of the explosion's damaging rays.                                | `1000`        |
| `damage`                  | Damage dealt by the explosion itself.                                       | `0.35`        |
| `damage_mortals`          | If `1`, the explosion damages mortal entities.                              | `1`           |
| `physics_explosion_power` | Controls the force of the physics-based explosion.                          | `0.2` to `0.6`|
| `stains_enabled`          | If `1`, the explosion leaves stains.                                        | `1`           |
| `light_r`, `light_g`, `light_b` | RGB values for the light emitted by the explosion.                        | `80`, `10`, `70`|

```xml
  <ProjectileComponent
    _enabled="1"
    lob_min="0.8"
    lob_max="1.1"
    speed_min="1450"
    speed_max="1850"
    direction_random_rad="0.003"
    on_death_explode="1"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
    die_on_liquid_collision="1"
    lifetime="20"
    velocity_sets_scale="1"
    velocity_sets_scale_coeff="2"
    camera_shake_when_shot="2.0"
    damage="1"
    knockback_force="3.0"
    >
	<config_explosion
		camera_shake="1.5"
		explosion_radius="3"
		explosion_sprite="data/particles/explosion_016_plasma_pink.xml"
		create_cell_material="plasma_fading"
		create_cell_probability="15"
		hole_enabled="1"
		ray_energy="1000"
		damage="0.35"
		damage_mortals="1"
		physics_explosion_power.min="0.2"
		physics_explosion_power.max="0.6"
		stains_enabled="1"
		light_r="80"
		light_g="10"
		light_b="70">
	</config_explosion>
  </ProjectileComponent>
```

## Light Component

This component adds a light source to the projectile, affecting the surrounding environment's illumination.

| Attribute | Description                               | Example Value |
| :-------- | :---------------------------------------- | :------------ |
| `radius`  | The radius of the light effect.           | `150`         |
| `r`, `g`, `b` | RGB color values for the light.           | `120`, `30`, `90` |

```xml
  <LightComponent
    _enabled="1"
    radius="150"
    r="120"
    g="30"
    b="90">
  </LightComponent>
```

## Particle Emitter Component

This component is responsible for emitting cosmetic particles, creating visual effects like trails.

| Attribute                 | Description                                                                 | Example Value |
| :------------------------ | :-------------------------------------------------------------------------- | :------------ |
| `emitted_material_name`   | The name of the material to be emitted as particles.                        | `plasma_fading_pink` |
| `is_trail`                | If `1`, the particles form a trail behind the projectile.                   | `1`           |
| `trail_gap`               | The spacing between emitted particles in a trail.                           | `0.5`         |
| `lifetime_min`, `lifetime_max` | The minimum and maximum lifetime of emitted particles.                      | `0.1`, `0.8`  |
| `emit_cosmetic_particles` | If `1`, emits particles that are purely cosmetic.                           | `1`           |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls how frequently particles are emitted in frames.                  | `1`, `2`      |

```xml
  <ParticleEmitterComponent
    emitted_material_name="plasma_fading_pink"
    x_vel_min="0"
    x_vel_max="0"
    y_vel_min="-2"
    y_vel_max="2"
    count_min="1"
    count_max="2"
	is_trail="1"
	trail_gap="0.5"
    lifetime_min="0.1"
    lifetime_max="0.8"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
    is_emitting="1" >
  </ParticleEmitterComponent>
```

## Audio Component

Defines the sound effects associated with the projectile.

| Attribute   | Description                               | Example Value                       |
| :---------- | :---------------------------------------- | :---------------------------------- |
| `file`      | Path to the audio bank file.              | `data/audio/Desktop/projectiles.bank` |
| `event_root`| The root event name for projectile sounds.| `projectiles/laser_lasergun`        |

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="projectiles/laser_lasergun">
  </AudioComponent>
```

## Variable Storage Component

Stores variables associated with the entity. In this case, it stores the projectile's own file path.

| Attribute    | Description                               | Example Value                         |
| :----------- | :---------------------------------------- | :------------------------------------ |
| `name`       | The name of the variable.                 | `projectile_file`                     |
| `value_string` | The string value of the variable.         | `data/entities/projectiles/laser_lasergun.xml` |

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/laser_lasergun.xml"
		>
	</VariableStorageComponent>
```