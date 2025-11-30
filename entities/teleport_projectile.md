---
title: Teleport Projectile
category: entities
---

# Teleport Projectile

This document describes the configuration for a teleport projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is defined as a player projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

## Base Projectile Configuration

Inherits base projectile properties, with specific adjustments to physics.

### VelocityComponent

*   **gravity\_y**: `0` - No vertical gravity applied.
*   **air\_friction**: `1.7` - Moderate air resistance.
*   **mass**: `0.04` - Low mass.

```xml
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
		  gravity_y="0"
		  air_friction="1.7"
		  mass="0.04"
		  >
		</VelocityComponent>
	</Base>
```

## Teleport Projectile Specifics

### TeleportProjectileComponent

*   **min\_distance\_from\_wall**: `4` - The minimum distance the projectile must maintain from walls when teleporting.

```xml
  <TeleportProjectileComponent
    min_distance_from_wall="4">
  </TeleportProjectileComponent>
```

## Projectile Component

This component governs the projectile's behavior, including its movement, effects, and interactions.

### Key Attributes

*   **_enabled**: `1` - Enables the component.
*   **lob\_min/lob\_max**: `0.5`/`0.7` - Controls the lobbing behavior (arc of the projectile).
*   **speed\_min/speed\_max**: `0`/`0` - The projectile has no initial speed.
*   **friction**: `1` - Standard friction.
*   **direction\_random\_rad**: `0.00` - No random deviation in direction.
*   **on\_death\_explode**: `1` - The projectile explodes upon death.
*   **on\_lifetime\_out\_explode**: `1` - The projectile explodes when its lifetime expires.
*   **explosion\_dont\_damage\_shooter**: `1` - The explosion does not harm the entity that fired it.
*   **on\_collision\_die**: `0` - The projectile does not die on collision.
*   **on\_collision\_remove\_projectile**: `0` - The projectile is not removed on collision.
*   **lifetime**: `240` - The projectile exists for 240 frames.
*   **lifetime\_randomness**: `7` - Slight randomness in lifetime.
*   **damage**: `0` - The projectile itself deals no damage.
*   **penetrate\_entities**: `1` - Can pass through entities.
*   **muzzle\_flash\_file**: `data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher_blue.xml` - Specifies the muzzle flash particle effect.
*   **shoot\_light\_flash\_radius/r/g/b**: `120`/`140`/`210`/`255` - Defines the light flash properties when shot.

### config\_explosion

Defines the properties of the explosion that occurs when the projectile dies or its lifetime ends.

*   **damage**: `0.0` - The explosion deals no direct damage.
*   **camera\_shake**: `0.5` - Causes moderate camera shake.
*   **explosion\_radius**: `2` - The radius of the explosion.
*   **explosion\_sprite**: `data/particles/explosion_008.xml` - The visual sprite for the explosion.
*   **hole\_enabled**: `1` - Creates a hole in the environment.
*   **ray\_energy**: `40000` - High energy for environmental destruction.
*   **shake\_vegetation**: `1` - Shakes vegetation in the explosion radius.
*   **stains\_enabled**: `1` - Leaves stains on surfaces.
*   **stains\_radius**: `3` - The radius of the stains.

```xml
  <ProjectileComponent
    _enabled="1"
    lob_min="0.5"
    lob_max="0.7"
    speed_min="0"
    speed_max="0"
    friction="1"
    direction_random_rad="0.00"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="0"
    on_collision_remove_projectile="0"
    lifetime="240"
    damage="0"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.005"
    hit_particle_force_multiplier="0.1"
    create_shell_casing="0"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher_blue.xml"
    shoot_light_flash_radius="120"
	shoot_light_flash_r="140"
	shoot_light_flash_g="210"
	shoot_light_flash_b="255"
	penetrate_entities="1"
	>
    <config_explosion
      never_cache="1"
      damage="0.0"
      camera_shake="0.5"
      explosion_radius="2"
      explosion_sprite="data/particles/explosion_008.xml"
      explosion_sprite_lifetime="0"
      create_cell_probability="0"
      hole_destroy_liquid="0"
	  explosion_sprite_additive="1"
      hole_enabled="1"
      ray_energy="40000"
      particle_effect="0"
      damage_mortals="1"
	  physics_explosion_power.min="0"
      physics_explosion_power.max="0"
      physics_throw_enabled="0"
      shake_vegetation="1"
      sparks_count_max="20"
      sparks_count_min="7"
      sparks_enabled="0"
      material_sparks_enabled="1"
      material_sparks_count_max="2"
      material_sparks_count_min="0"
      light_enabled="0"
      stains_enabled="1"
      stains_radius="3" >
    </config_explosion>
  </ProjectileComponent>
```

## Audio Component

### AudioComponent

*   **file**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank.
*   **event\_root**: `player_projectiles/teleport` - The root event for teleport projectile sounds.

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/teleport">
  </AudioComponent>
```

## Particle Emitter Component

### ParticleEmitterComponent

This component defines the particles emitted by the projectile.

*   **emitted\_material\_name**: `spark_blue` - The material of the emitted particles.
*   **offset.x/y**: `2`/`0` - Offset for particle emission.
*   **gravity.y**: `0.0` - No gravity for emitted particles.
*   **x\_vel\_min/max**: `-20`/`20` - Velocity range for emitted particles on the X-axis.
*   **y\_vel\_min/max**: `-20`/`20` - Velocity range for emitted particles on the Y-axis.
*   **count\_min/max**: `1`/`1` - Number of particles emitted per burst.
*   **lifetime\_min/max**: `0.65`/`1.2` - Lifetime range for emitted particles.
*   **emit\_real\_particles**: `0` - Emits cosmetic particles.
*   **render\_on\_grid**: `1` - Particles are rendered on the game grid.
*   **airflow\_force/time/scale**: `0.3`/`0.01`/`0.05` - Airflow properties affecting particles.
*   **emission\_interval\_min/max\_frames**: `1`/`2` - Interval between particle emissions.
*   **area\_circle\_radius.max**: `2` - The maximum radius of the emission area.
*   **fade\_based\_on\_lifetime**: `1` - Particles fade out as their lifetime decreases.
*   **is\_emitting**: `1` - The emitter is active.

```xml
  <ParticleEmitterComponent
    emitted_material_name="spark_blue"
    offset.x="2"
    offset.y="0"
	gravity.y="0.0"
	x_vel_min="-20"
    x_vel_max="20"
    y_vel_min="-20"
    y_vel_max="20"
    count_min="1"
    count_max="1"
    lifetime_min="0.65"
    lifetime_max="1.2"
    emit_real_particles="0"
	render_on_grid="1"
	airflow_force="0.3"
	airflow_time="0.01"
	airflow_scale="0.05"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
	area_circle_radius.max="2"
	fade_based_on_lifetime="1"
    is_emitting="1" >
  </ParticleEmitterComponent>
```