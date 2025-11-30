---
title: Megalaser Beam Projectile
category: entities
---

# Megalaser Beam Projectile

This document details the `megalaser_beam.xml` entity, which defines the behavior and appearance of the Megalaser Beam projectile in Noita. This projectile is designed to be a powerful, albeit potentially short-lived, beam attack.

## Core Components

The Megalaser Beam projectile is built upon several core Noita entity components, each contributing to its functionality.

### Entity Definition

```xml
<Entity 
	name="$projectile_default" tags="projectile_player,megalaser_beam"
	>
	<!-- fail safe lifetime to make sure if these do end up just hanging around, they'll eventually die -->
	<LifetimeComponent lifetime="360" ></LifetimeComponent>
		
	<!-- all components are disabled on init. activated by megalaser_launch.lua -->
	
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			_enabled="0"
			air_friction="-50"
			gravity_y="0"
			mass="0.04"
			>
		</VelocityComponent> 
	</Base>
    
    <!-- ... other components ... -->

</Entity>
```

*   **`name="$projectile_default"`**: Inherits default projectile properties.
*   **`tags="projectile_player,megalaser_beam"`**: Identifies the projectile as player-controlled and specifically as a Megalaser Beam.
*   **`LifetimeComponent lifetime="360"`**: A failsafe to ensure the projectile eventually despawns if it remains active indefinitely.
*   **`Base file="data/entities/base_projectile.xml"`**: Inherits fundamental projectile behaviors.
    *   **`VelocityComponent _enabled="0"`**: The velocity component is initially disabled and controlled by the `megalaser_launch.lua` script.
        *   **`air_friction="-50"`**: High negative air friction, suggesting rapid acceleration or resistance to slowing down.
        *   **`gravity_y="0"`**: No vertical gravity applied.
        *   **`mass="0.04"`**: A very low mass, indicating it's easily influenced by forces.

### Projectile Component

This is the primary component defining the projectile's behavior in flight and upon death.

```xml
	<ProjectileComponent 
		_enabled="0"
		lob_min="0.8"
		lob_max="1.0"
		speed_min="40"
		speed_max="40"
		die_on_liquid_collision="1"
		on_death_explode="1"
		on_death_gfx_leave_sprite="0" 
		on_lifetime_out_explode="1"
		explosion_dont_damage_shooter="1" 
		on_collision_die="1"
		shoot_light_flash_radius="15"
		shoot_light_flash_r="250"
		shoot_light_flash_g="80"
		shoot_light_flash_b="255"
		velocity_sets_scale="1"
		damage="1"
		lifetime="180"
		penetrate_entities="0"
		hit_particle_force_multiplier="0.25"
		knockback_force="1.5"
		bounces_left="10"
		ragdoll_force_multiplier="0.01"
		ragdoll_fx_on_collision="BLOOD_SPRAY"
		physics_impulse_coeff="5000"
		>
		<!-- ... config_explosion ... -->
	</ProjectileComponent>
```

*   **`_enabled="0"`**: Disabled on initialization, activated by script.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Defines a very narrow range for projectile lob, suggesting a mostly straight trajectory.
*   **`speed_min="40"`, `speed_max="40"`**: Fixed speed of 40.
*   **`die_on_liquid_collision="1"`**: The projectile will be destroyed upon hitting liquids.
*   **`on_death_explode="1"`**: Explodes when it dies.
*   **`on_lifetime_out_explode="1"`**: Explodes when its lifetime expires.
*   **`on_collision_die="1"`**: Dies upon colliding with anything.
*   **`shoot_light_flash_radius="15"`, `shoot_light_flash_r="250"`, `shoot_light_flash_g="80"`, `shoot_light_flash_b="255"`**: Creates a bright, purplish-pink light flash upon firing.
*   **`damage="1"`**: Base damage dealt by the projectile.
*   **`lifetime="180"`**: The projectile's active lifetime in frames.
*   **`penetrate_entities="0"`**: Does not penetrate other entities.
*   **`knockback_force="1.5"`**: Applies a knockback force to targets.
*   **`bounces_left="10"`**: Can bounce up to 10 times.
*   **`physics_impulse_coeff="5000"`**: A high coefficient for physics impulse, suggesting strong interactions.

#### `config_explosion`

Details the explosion effect when the projectile dies.

```xml
		<config_explosion
			never_cache="1" 
			camera_shake="4.5" 
			explosion_radius="3"
			explosion_sprite="data/particles/explosion_016_plasma_green.xml" 
			create_cell_material="plasma_fading_green"
			create_cell_probability="15" 
			hole_enabled="1"
			ray_energy="100000"
			damage="0.22"
			hole_image="data/temp/explosion_hole.png" 
			damage_mortals="1" 
			physics_explosion_power.min="0.2" 
			physics_explosion_power.max="0.35" 
			shake_vegetation="1" 
			stains_enabled="1"
			stains_radius="4" 
			light_fade_time="0.2"
			light_r="10"
			light_g="30"
			light_b="10">
		</config_explosion>
```

*   **`camera_shake="4.5"`**: Significant camera shake on explosion.
*   **`explosion_radius="3"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_016_plasma_green.xml"`**: Uses a specific green plasma explosion sprite.
*   **`create_cell_material="plasma_fading_green"`**: Creates fading green plasma cells upon explosion.
*   **`ray_energy="100000"`**: High energy for potential ray interactions.
*   **`damage="0.22"`**: Deals a small amount of damage to mortals.
*   **`physics_explosion_power.min="0.2"`, `physics_explosion_power.max="0.35"`**: Moderate physics explosion power.
*   **`shake_vegetation="1"`**: Shakes vegetation in the explosion radius.
*   **`stains_enabled="1"`, `stains_radius="4"`**: Creates stains on surfaces.

### Sprite Component

Defines the visual representation of the projectile.

```xml
	<SpriteComponent 
		_enabled="0"
		emissive="0"
		image_file="data/projectiles_gfx/laser_green_big.xml" 
		>
	</SpriteComponent>
```

*   **`_enabled="0"`**: Disabled on initialization.
*   **`image_file="data/projectiles_gfx/laser_green_big.xml"`**: Uses a large green laser graphic.

### Particle Emitters

Two particle emitters are used to create visual effects for the beam.

#### Solid Particle Line Emitter

```xml
	<ParticleEmitterComponent 
		_enabled="0"
		emitted_material_name="plasma_fading_green"
		count_min="1"
		count_max="1"
		is_trail="1"
		trail_gap="1"
		lifetime_min="0.4"
		lifetime_max="0.4"
		emit_real_particles="0"
		render_on_grid="0"
		collide_with_grid="0"
		fade_based_on_lifetime="0"
		emit_cosmetic_particles="1"
		draw_as_long="0"
		emission_interval_min_frames="1"
		emission_interval_max_frames="1"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

*   **`emitted_material_name="plasma_fading_green"`**: Emits fading green plasma particles.
*   **`is_trail="1"`, `trail_gap="1"`**: Creates a continuous trail with minimal gaps.
*   **`lifetime_min="0.4"`, `lifetime_max="0.4"`**: Short particle lifetime.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.

#### Secondary Sprinkles Emitter

```xml
	<ParticleEmitterComponent 
		_enabled="0"
		emitted_material_name="plasma_fading_green"
		y_vel_min="-5"
		y_vel_max="5"
		count_min="1"
		count_max="1"
		is_trail="1"
		trail_gap="5"
		lifetime_min="0.2"
		lifetime_max="0.8"
		emit_real_particles="0"
		render_on_grid="1"
		emit_cosmetic_particles="1"
		fade_based_on_lifetime="0"
		emission_interval_min_frames="1"
		emission_interval_max_frames="2"
		is_emitting="1" >
	</ParticleEmitterComponent>
```

*   **`emitted_material_name="plasma_fading_green"`**: Also emits fading green plasma particles.
*   **`y_vel_min="-5"`, `y_vel_max="5"`**: Particles have a slight vertical velocity spread.
*   **`trail_gap="5"`**: Larger gap between particles, creating a more scattered effect.
*   **`lifetime_min="0.2"`, `lifetime_max="0.8"`**: Variable particle lifetime.

### Audio Component

Defines the sound effects associated with the projectile.

```xml
	<AudioComponent
		file="data/audio/Desktop/projectiles.bank"
		event_root="player_projectiles/megalaser_beam">
	</AudioComponent>
```

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank.
*   **`event_root="player_projectiles/megalaser_beam"`**: Links to the specific sound events for the Megalaser Beam.

## Script Interaction

The comment `<!-- all components are disabled on init. activated by megalaser_launch.lua -->` indicates that the projectile's behavior is primarily controlled by an external Lua script (`megalaser_launch.lua`). This script is responsible for enabling the relevant components and dictating when and how the Megalaser Beam is fired.

## Key Attributes for Modding

When modifying this entity, consider the following key attributes:

*   **`ProjectileComponent`**:
    *   `damage`: Adjust the base damage.
    *   `lifetime`: Control how long the beam persists.
    *   `knockback_force`: Modify the impact on enemies.
    *   `bounces_left`: Change its ability to ricochet.
    *   `speed_min`/`speed_max`: Alter projectile velocity.
*   **`config_explosion`**:
    *   `explosion_radius`: Affect the area of effect upon death.
    *   `camera_shake`: Tune the visual feedback of the explosion.
    *   `damage`: Modify explosion damage.
    *   `ray_energy`: Impact interactions with environmental elements.
*   **`SpriteComponent`**:
    *   `image_file`: Change the visual appearance of the beam.
*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name`: Change the type of particles emitted.
    *   `count_min`/`count_max`: Adjust particle density.
    *   `lifetime_min`/`lifetime_max`: Control particle duration.
    *   `trail_gap`: Modify the continuity of particle trails.
*   **`AudioComponent`**:
    *   `event_root`: Change the associated sound effects.