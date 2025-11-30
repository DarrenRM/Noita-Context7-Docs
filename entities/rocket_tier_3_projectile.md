---
title: Rocket Tier 3 Projectile
category: entities
---

# Rocket Tier 3 Projectile

This document details the configuration for the "Rocket Tier 3" projectile in Noita, focusing on its attributes and effects for AI-assisted modding.

## Core Projectile Properties

The `Entity` tag defines the base projectile with player-targeting and rocket properties.

```xml
<Entity name="$projectile_default" tags="projectile_player,rocket" >
```

### Base Projectile Configuration

The `Base` tag inherits common projectile behaviors.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="50"
        air_friction="-5.0"
		mass="0.05"
		>
    </VelocityComponent>
</Base>
```

*   **`gravity_y`**: Controls the downward acceleration of the projectile.
*   **`air_friction`**: Negative values increase air resistance, slowing the projectile.
*   **`mass`**: Affects how the projectile interacts with physics.

### Projectile Component - Key Attributes

This component defines the unique behaviors and effects of the rocket.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.8"
    lob_max="1.0"
    speed_min="70"
    speed_max="100"
    direction_random_rad="0.0"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="0"
    on_collision_die="1"
    lifetime="360"
    damage="5"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.04"
    hit_particle_force_multiplier="5.5 "
    camera_shake_when_shot="15.0"
	muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher.xml"
    shoot_light_flash_r="215"
    shoot_light_flash_g="40"
    shoot_light_flash_b="255"
    shoot_light_flash_radius="90"
	knockback_force="4.0"
	physics_impulse_coeff="5000"
	>
    <!-- ... config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min`/`lob_max`**: Controls the arc of the projectile.
*   **`speed_min`/`speed_max`**: Defines the projectile's initial velocity range.
*   **`on_death_explode`**: Triggers an explosion upon death (e.g., collision or lifetime end).
*   **`on_lifetime_out_explode`**: Ensures explosion if lifetime expires.
*   **`on_collision_die`**: The projectile is destroyed upon hitting something.
*   **`lifetime`**: Duration in frames before the projectile expires.
*   **`damage`**: Base damage dealt by the projectile.
*   **`camera_shake_when_shot`**: Intensity of camera shake when the projectile is fired.
*   **`muzzle_flash_file`**: Specifies the particle effect for the muzzle flash.
*   **`shoot_light_flash_r/g/b/radius`**: Defines the color and radius of the light emitted when shot.
*   **`knockback_force`**: The force applied to entities hit by the projectile.
*   **`physics_impulse_coeff`**: Affects the strength of physics interactions.

#### Explosion Configuration (`config_explosion`)

Details of the explosion effect when the projectile detonates.

```xml
    <config_explosion
      never_cache="1"
      camera_shake="90"
      explosion_radius="42"
      explosion_sprite="data/particles/explosion_032_pink.xml"
      explosion_sprite_lifetime="0"
      load_this_entity="data/entities/particles/particle_explosion/main_swirly_purple.xml"
      create_cell_probability="40"
      cell_explosion_power_ragdoll_coeff="0.5"
      hole_destroy_liquid="0"
      explosion_sprite_additive="1"
      hole_enabled="1"
      ray_energy="6200000"
      damage="5.2"
      particle_effect="1"
      damage_mortals="1"
      physics_explosion_power.min="1.0"
      physics_explosion_power.max="1.4"
      physics_throw_enabled="1"
      shake_vegetation="1"
      sparks_count_max="50"
      sparks_count_min="30"
	  spark_material="spark_purple_bright"
      sparks_enabled="1"
      stains_enabled="1"
      stains_radius="20"
      audio_event_name="explosions/magic_rocket_big" >
    </config_explosion>
```

*   **`camera_shake`**: Intensity of camera shake during the explosion.
*   **`explosion_radius`**: The area of effect for the explosion.
*   **`explosion_sprite`**: The visual sprite used for the explosion.
*   **`load_this_entity`**: Specifies an entity to spawn upon explosion (e.g., custom particle effects).
*   **`ray_energy`**: The energy value for any resulting magical rays.
*   **`damage`**: Damage dealt by the explosion itself.
*   **`physics_explosion_power.min/max`**: Controls the force of the physics-based explosion.
*   **`sparks_count_min/max`**: Number of sparks generated.
*   **`spark_material`**: The material/type of sparks created.
*   **`audio_event_name`**: The sound effect played for the explosion.

### Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/fireball_small.xml"
    >
</SpriteComponent>
```

*   **`image_file`**: Path to the sprite asset.

### Light Component

Adds a light source to the projectile.

```xml
<LightComponent
    _enabled="1"
    r="100"
    g="10"
    b="255"
    radius="150" >
</LightComponent>
```

*   **`r/g/b`**: RGB color values for the light.
*   **`radius`**: The range of the light.

### Particle Emitters

Multiple emitters contribute to the visual effects of the rocket, including smoke and sparks.

```xml
<!-- Smoke Trail -->
<ParticleEmitterComponent
    emitted_material_name="smoke"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="-1"
    y_pos_offset_min="-1"
    x_pos_offset_max="1"
    y_pos_offset_max="1"
    x_vel_min="-10"
    x_vel_max="10"
    y_vel_min="-10"
    y_vel_max="10"
    count_min="5"
    count_max="5"
    lifetime_min="0.1"
    lifetime_max="0.3"
    create_real_particles="1"
    emit_cosmetic_particles="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1" >
</ParticleEmitterComponent>

<!-- Various Spark Trails -->
<ParticleEmitterComponent
    emitted_material_name="spark_purple_bright"
    offset.x="0"
    offset.y="0"
    count_min="1"
    count_max="8"
    gravity.y="10"
    lifetime_min="0.3"
    lifetime_max="0.5"
    airflow_force="0.6"
    airflow_time="0.1"
    airflow_scale="0.03"
    is_trail="1"
    trail_gap="0.5"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    create_real_particles="0"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
    is_emitting="1" >
</ParticleEmitterComponent>

<!-- Sparse Emitter -->
<ParticleEmitterComponent
    emitted_material_name="spark_purple_bright"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="0"
    x_pos_offset_max="0"
    y_pos_offset_min="0"
    y_pos_offset_max="0"
    x_vel_min="10"
    x_vel_max="20"
    y_vel_min="0"
    y_vel_max="0"
    gravity.y="0.0"
    count_min="1"
    count_max="1"
    lifetime_min="1.4"
    lifetime_max="2.5"
    is_trail="0"
    trail_gap="8.0"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    airflow_force="0.5"
    airflow_time="0.5"
    airflow_scale="0.05"
    emission_interval_min_frames="8"
    emission_interval_max_frames="12"
    emit_cosmetic_particles="1"
    create_real_particles="0"
    is_emitting="1" >
</ParticleEmitterComponent>

<!-- Larger Spark Burst -->
<ParticleEmitterComponent
    emitted_material_name="spark_purple_bright"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="-2"
    y_pos_offset_min="-2"
    x_pos_offset_max="2"
    y_pos_offset_max="2"
    x_vel_min="-10"
    x_vel_max="10"
    y_vel_min="-10"
    y_vel_max="10"
    count_min="10"
    count_max="20"
    lifetime_min="1.6"
    lifetime_max="3.9"
    create_real_particles="0"
    emit_cosmetic_particles="1"
	render_on_grid="1"
	gravity.y="20"
	fade_based_on_lifetime="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: The type of particle to emit (e.g., "smoke", "spark_purple_bright").
*   **`count_min/max`**: The number of particles emitted per interval.
*   **`lifetime_min/max`**: Duration of each particle.
*   **`is_trail`**: If `1`, particles form a trail.
*   **`create_real_particles`**: If `1`, particles have physics and can interact.
*   **`emit_cosmetic_particles`**: If `1`, particles are purely visual.

### Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_rocket">
</AudioComponent>
```

*   **`file`**: The audio bank file.
*   **`event_root`**: The specific sound event to trigger.

### Variable Storage Component

Stores the projectile's own file path, useful for referencing.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/rocket_tier_3.xml"
    >
</VariableStorageComponent>
```