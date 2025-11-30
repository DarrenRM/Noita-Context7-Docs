---
title: Pollen Projectile
category: entities
---

# Pollen Projectile

This document details the configuration for the "Pollen" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The `Entity` tag defines the fundamental properties of the projectile.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player,hittable"
   >
   
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent
			gravity_y="10"
			air_friction="2.8"
			mass="0.35"
			>
		</VelocityComponent>
	</Base>

  <!-- ... other components ... -->

</Entity>
```

*   **`name`**: `$projectile_default` - Inherits default projectile naming.
*   **`tags`**: `projectile_player,hittable` - Identifies it as a player projectile and something that can be hit.

## Projectile Component

This is the primary component defining the projectile's behavior.

```xml
  <ProjectileComponent 
    _enabled="1" 
    lob_min="0.5"
    lob_max="0.7"
    speed_min="150"
    speed_max="250"
    friction="1"
    direction_random_rad="0.01"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
    lifetime="750"
    damage="0.2"
    lifetime_randomness="100"
    ragdoll_force_multiplier="0"
    hit_particle_force_multiplier="0.1"
    create_shell_casing="0"
    muzzle_flash_file=""
    shoot_light_flash_radius="0"
    collide_with_shooter_frames="6"
    bounces_left="1"
    friendly_fire="1"
    velocity_sets_scale="0"
    velocity_sets_rotation="0"
	knockback_force="1.0"
	physics_impulse_coeff="500"
    >
    <!-- ... config_explosion ... -->
  </ProjectileComponent>
```

**Key Attributes:**

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile (0.5 to 0.7).
*   **`speed_min`, `speed_max`**: Sets the projectile's speed range (150 to 250).
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile dies upon collision.
*   **`lifetime`**: `750` - The maximum duration of the projectile in frames.
*   **`lifetime_randomness`**: `100` - Adds variability to the projectile's lifetime.
*   **`damage`**: `0.2` - The base damage dealt by the projectile.
*   **`bounces_left`**: `1` - Allows the projectile to bounce once.
*   **`knockback_force`**: `1.0` - The force applied to knock back entities on hit.

### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion when the projectile dies.

```xml
    <config_explosion
      never_cache="1" 
      camera_shake="0.5" 
      explosion_radius="7"
      explosion_sprite="data/particles/explosion_012_poof.xml" 
      explosion_sprite_lifetime="0" 
      create_cell_probability="0" 
      hole_destroy_liquid="0" 
      hole_enabled="1" 
      damage="0.2"
      ray_energy="200000"
	  max_durability_to_destroy="10"
      hole_image="data/temp/explosion_hole.png" 
      particle_effect="0" 
      damage_mortals="1"
	  physics_explosion_power.min="0.05" 
      physics_explosion_power.max="0.12" 
      physics_throw_enabled="1" 
      shake_vegetation="1" 
      sparks_enabled="0"
      material_sparks_enabled="1"
      material_sparks_count_max="1"
      material_sparks_count_min="0" 
      gore_particle_count="6"
      light_fade_time="0.029"
      stains_enabled="1"
      stains_radius="2"
      audio_enabled="0" >
    </config_explosion>
```

**Key Attributes:**

*   **`camera_shake`**: `0.5` - The intensity of camera shake on explosion.
*   **`explosion_radius`**: `7` - The radius of the explosion effect.
*   **`explosion_sprite`**: `data/particles/explosion_012_poof.xml` - The visual effect for the explosion.
*   **`hole_enabled`**: `1` - Creates a hole in terrain upon explosion.
*   **`damage`**: `0.2` - Damage dealt by the explosion itself.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: Controls the force of the physics-based explosion.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake from the explosion.
*   **`stains_enabled`**: `1` - Enables stain effects from the explosion.
*   **`stains_radius`**: `2` - The radius of the stain effect.

## Sprite Component

Defines the visual appearance of the projectile.

```xml
  <SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/pollen.xml" 
    has_special_scale="1"
	special_scale_x="1"
	special_scale_y="1"
     >
  </SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/pollen.xml` - Specifies the sprite sheet or animation file.

## Particle Emitter Component

Controls the emission of particles from the projectile.

```xml
  <ParticleEmitterComponent 
		emitted_material_name="spark_white"
		offset.x="-2"
		offset.y="0"
		x_pos_offset_min="-4"
		x_pos_offset_max="4"
		y_pos_offset_min="-4"
		y_pos_offset_max="4"
		x_vel_min="0"
		x_vel_max="0"
		y_vel_min="0"
		y_vel_max="0"
		gravity.y="0.0"
		count_min="1"
		count_max="1"
		lifetime_min="1.3"
		lifetime_max="3.5"
		render_on_grid="1"
		fade_based_on_lifetime="1"
		airflow_force="1.1"
		airflow_time="0.901"
		airflow_scale="0.1833"
		emission_interval_min_frames="1"
		emission_interval_max_frames="5"
		emit_cosmetic_particles="1"
		create_real_particles="0"
		is_emitting="1"
    >
	</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `spark_white` - The material of the particles emitted.
*   **`lifetime_min`, `lifetime_max`**: Controls the duration of emitted particles.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: Parameters for how airflow affects the particles.

## Audio Component

Manages the sound effects associated with the projectile.

```xml
  <AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/bullet_arrow">
  </AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
*   **`event_root`**: `player_projectiles/bullet_arrow` - The specific sound event to trigger.

## Homing Component

Enables homing behavior for the projectile.

```xml
	<HomingComponent
		homing_targeting_coeff="10.0"
		homing_velocity_multiplier="0.89"
	>
	</HomingComponent>
```

*   **`homing_targeting_coeff`**: `10.0` - The strength of the homing targeting.
*   **`homing_velocity_multiplier`**: `0.89` - How much the homing affects the projectile's velocity.

## Hitbox Component

Defines the collision area of the projectile.

```xml
	<HitboxComponent 
        _enabled="1" 
        aabb_min_x="-5" 
        aabb_max_x="5" 
        aabb_min_y="-5" 
        aabb_max_y="5" >
    </HitboxComponent>
```

*   **`aabb_min_x`, `aabb_max_x`, `aabb_min_y`, `aabb_max_y`**: Defines the bounding box for collisions.

## Damage Model Component

Specifies how the projectile interacts with damage and health.

```xml
    <DamageModelComponent 
        _enabled="1" 
        hp="0.2"
        fire_probability_of_ignition="0" 
        falling_damages="0" 
        air_needed="0" 
        materials_damage="0"
        blood_material="fungisoil"
        blood_multiplier="0"
        create_ragdoll="0" >
		<damage_multipliers
			explosion="0.0"
			>
		</damage_multipliers>
    </DamageModelComponent>
```

*   **`hp`**: `0.2` - The health of the projectile itself.
*   **`blood_material`**: `fungisoil` - The material that appears as "blood" when the projectile is damaged.
*   **`damage_multipliers`**: Allows for specific damage type modifications. `explosion="0.0"` means it takes no damage from explosions.