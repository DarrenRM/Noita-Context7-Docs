---
title: Holy Lance Projectile
category: data/entities
---

# Holy Lance Projectile

This document details the configuration for the "Holy Lance" projectile in Noita, intended for AI-assisted modding.

## Core Components

The Holy Lance projectile is defined by several key components that dictate its behavior, appearance, and effects.

### Entity Definition

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

*   **`name="$projectile_default"`**: A base name, often overridden by specific projectile types.
*   **`tags="projectile_player"`**: Identifies this entity as a projectile fired by the player.

### Base Projectile Configuration

```xml
<Base file="data/entities/base_projectile.xml" >
	<VelocityComponent
		gravity_y="100"
		air_friction="-0.6"
		mass="0.15"
		>
	</VelocityComponent>
</Base>
```

*   **`gravity_y="100"`**: Applies a downward gravitational force.
*   **`air_friction="-0.6"`**: Reduces velocity over time due to air resistance.
*   **`mass="0.15"`**: Defines the projectile's mass, influencing its interaction with physics.

### Projectile Component - Key Attributes

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.8"
    lob_max="1.1"
    speed_min="100"
    speed_max="200"
    direction_random_rad="0.003"
    on_death_explode="1"
    on_lifetime_out_explode="1"
    on_collision_die="1"
    lifetime="300"
    ground_penetration_coeff="6"
    bounces_left="3"
    collide_with_shooter_frames="4"
    penetrate_entities="1"
    friendly_fire="1"
    damage="0"
    knockback_force="1.5"
    >
    <damage_by_type
        holy="1.75"
    >
	</damage_by_type>
    <config_explosion
      damage="1.2"
      explosion_radius="30"
      explosion_sprite="data/particles/explosion_032.xml"
      hole_enabled="1"
      hole_image="data/temp/explosion_hole.png"
      ray_energy="100000"
      sparks_count_min="7"
      sparks_count_max="15"
      spark_material="gold"
      light_enabled="1"
      light_r="40"
      light_g="120"
      light_b="180"
      stains_enabled="1"
      stains_radius="1">
    </config_explosion>
</ProjectileComponent>
```

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile.
*   **`speed_min`, `speed_max`**: Defines the range of projectile speeds.
*   **`direction_random_rad`**: Introduces slight randomness to the projectile's trajectory.
*   **`on_death_explode="1"`**: Causes the projectile to explode upon death (e.g., hitting a surface or running out of lifetime).
*   **`on_lifetime_out_explode="1"`**: Explodes when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile dies upon collision.
*   **`lifetime="300"`**: The duration in frames before the projectile expires.
*   **`ground_penetration_coeff="6"`**: How effectively it penetrates ground.
*   **`bounces_left="3"`**: Number of bounces allowed.
*   **`collide_with_shooter_frames="4"`**: Frames before it can collide with the shooter.
*   **`penetrate_entities="1"`**: Allows penetration of other entities.
*   **`friendly_fire="1"`**: Can damage allies.
*   **`damage="0"`**: Base damage is 0, damage is applied via `damage_by_type`.
*   **`knockback_force="1.5"`**: The force applied to knock back targets.
*   **`damage_by_type`**: Specifies damage multipliers for different damage types. `holy="1.75"` indicates a significant bonus to holy damage.
*   **`config_explosion`**: Defines the properties of the explosion effect upon death.
    *   `damage="1.2"`: Damage dealt by the explosion.
    *   `explosion_radius="30"`: The area of effect for the explosion.
    *   `explosion_sprite`: The visual effect used for the explosion.
    *   `hole_enabled="1"`: Creates a hole in surfaces.
    *   `ray_energy="100000"`: High energy for potential environmental destruction.
    *   `spark_material="gold"`: The material used for sparks.
    *   `light_enabled="1"`: Creates a light source upon explosion.

### Sprite Component

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/lance_holy.xml"
    additive="1"
     >
</SpriteComponent>
```

*   **`image_file="data/projectiles_gfx/lance_holy.xml"`**: Specifies the graphical asset for the projectile.
*   **`additive="1"`**: Uses additive blending for a brighter, more luminous effect.

### Particle Emitters

The Holy Lance utilizes multiple `ParticleEmitterComponent`s to create visual effects, primarily using "gold" material particles.

*   **Trail Emitter**: Creates a continuous trail of particles.
    *   `emitted_material_name="gold"`
    *   `is_trail="1"`
    *   `trail_gap="0.6"`
    *   `fade_based_on_lifetime="1"`
*   **Dense Emitter**: For a concentrated burst of particles.
    *   `count_min="1"`, `count_max="4"`
    *   `lifetime_min="0.2"`, `lifetime_max="0.3"`
*   **Sparse Emitter**: For more spread-out particles.
    *   `x_vel_min="20"`, `x_vel_max="40"`
    *   `lifetime_min="0.6"`, `lifetime_max="0.8"`
*   **Very Sparse Emitter**: For infrequent, longer-lasting particles.
    *   `emission_interval_min_frames="10"`, `emission_interval_max_frames="20"`
    *   `lifetime_min="1.4"`, `lifetime_max="1.5"`

### Light Component

```xml
<LightComponent
    _enabled="1"
    radius="60"
	r="255"
	g="210"
	b="150"
	>
</LightComponent>
```

*   **`radius="60"`**: The radius of the light emitted by the projectile.
*   **`r`, `g`, `b`**: Defines the color of the light (a warm, yellowish-white).

### Audio Component

```xml
<AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/bullet_arrow">
</AudioComponent>
```

*   **`file`**: Specifies the audio bank containing the sound effects.
*   **`event_root`**: The base event path for projectile sounds.

### Variable Storage Component

```xml
<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/lance_holy.xml"
		>
</VariableStorageComponent>
```

*   **`name="projectile_file"`**: Stores the path to this projectile's entity file, useful for referencing.