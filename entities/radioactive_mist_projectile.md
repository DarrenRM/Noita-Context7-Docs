---
title: Radioactive Mist Projectile
category: entities
---

# Radioactive Mist Projectile

This document describes the configuration for a radioactive mist projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity defines a projectile with player-specific properties.

```xml
<Entity tags="" name="$projectile_default" tags="projectile_player,projectile" >
	<!-- ... components ... -->
</Entity>
```

### Key Attributes:

*   **`tags`**: `projectile_player`, `projectile` - Identifies this entity as a player-owned projectile.

## Velocity Component

This component controls the projectile's movement physics.

```xml
<VelocityComponent
	gravity_y="0"
	air_friction="0"
	mass="0.00"
	>
</VelocityComponent>
```

### Key Attributes:

*   **`gravity_y`**: `0` - No vertical gravity applied.
*   **`air_friction`**: `0` - No air resistance.
*   **`mass`**: `0.00` - Negligible mass.

## Particle Emitter Component

This component is responsible for emitting the radioactive mist particles.

```xml
<ParticleEmitterComponent
	emitted_material_name="cloud_radioactive"
	offset.x="0"
	offset.y="0"
	x_pos_offset_min="0"
	x_pos_offset_max="0"
	y_pos_offset_min="0"
	y_pos_offset_max="0"
	x_vel_min="0"
	x_vel_max="0"
	y_vel_min="0"
	y_vel_max="0"
	count_min="1"
	count_max="10"
	emission_interval_min_frames="6"
	emission_interval_max_frames="6"
	image_animation_file="data/particles/image_emitters/cloud_circle.png"
	image_animation_loop="1"
	emit_cosmetic_particles="0"
	create_real_particles="1" >
</ParticleEmitterComponent>
```

### Key Attributes:

*   **`emitted_material_name`**: `cloud_radioactive` - Specifies the material of the particles being emitted.
*   **`count_min` / `count_max`**: `1` / `10` - Controls the number of particles emitted per interval.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `6` / `6` - Sets the frequency of particle emission.
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_circle.png` - The sprite used for the emitted particles.
*   **`create_real_particles`**: `1` - Ensures actual particles are created, not just cosmetic ones.

## Projectile Component

This component defines the behavior and properties of the projectile itself.

```xml
<ProjectileComponent
    _enabled="1"
	lob_min="0.1"
  	lob_max="1.0"
  	speed_min="0"
  	speed_max="0"
    die_on_low_velocity="0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="0"
	explosion_dont_damage_shooter="1"
    damage="0"
    on_collision_die="0"
    lifetime="500"
	knockback_force="0"
	damage_every_x_frames="25"
	>
	<!-- ... config_explosion ... -->
</ProjectileComponent>
```

### Key Attributes:

*   **`lob_min` / `lob_max`**: `0.1` / `1.0` - Controls the arc of the projectile.
*   **`speed_min` / `speed_max`**: `0` / `0` - The projectile has no initial speed.
*   **`lifetime`**: `500` - The projectile exists for 500 frames.
*   **`damage`**: `0` - The projectile itself deals no direct damage.
*   **`damage_every_x_frames`**: `25` - Indicates that damage (if any) would be applied periodically.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.

### Config Explosion:

This nested element defines explosion properties, which are largely disabled for this projectile.

```xml
	<config_explosion
		never_cache="1"
		camera_shake="0"
		explosion_radius="0"
		explosion_sprite=""
		explosion_sprite_lifetime="0.0"
		create_cell_probability="0"
		create_cell_material=""
		ray_energy="0"
		hole_enabled="0"
		particle_effect="0"
		damage_mortals="0"
		physics_throw_enabled="0"
		shake_vegetation="0"
		sparks_enabled="0"
		light_fade_time="0.1"
		stains_enabled="0"
		>
	</config_explosion>
```

## Audio Component

This component handles the sound effects associated with the projectile.

```xml
<AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/mist">
</AudioComponent>

<AudioLoopComponent
		file="data/audio/Desktop/projectiles.bank"
		event_name="player_projectiles/mist/loop"
		auto_play="1">
</AudioLoopComponent>
```

### Key Attributes:

*   **`file`**: `data/audio/Desktop/projectiles.bank` - Specifies the audio bank file.
*   **`event_root`**: `player_projectiles/mist` - The base event for the projectile's sounds.
*   **`event_name`**: `player_projectiles/mist/loop` - The specific event for the looping sound.
*   **`auto_play`**: `1` - The looping sound starts automatically.