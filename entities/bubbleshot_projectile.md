---
title: Bubbleshot Projectile
category: entities
---

# Bubbleshot Projectile

This document details the configuration of the `bubbleshot.xml` entity, which defines a player projectile in Noita.

## Entity Definition

The `bubbleshot.xml` entity represents a player-controlled projectile with specific behaviors and visual properties.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

### Key Attributes:

*   **`name="$projectile_default"`**: This is a placeholder name, indicating it inherits default projectile properties.
*   **`tags="projectile_player"`**: This tag identifies the entity as a projectile fired by the player.

## Base Projectile Configuration

The projectile inherits core functionality from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml" >
	<VelocityComponent
		gravity_y="0"
		air_friction="1.0"
		mass="0.02"
		>
	</VelocityComponent>
</Base>
```

### `VelocityComponent` Attributes:

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="1.0"`**: Standard air friction is applied.
*   **`mass="0.02"`**: Defines the projectile's mass.

## Projectile Component

This component governs the specific behavior and effects of the bubbleshot projectile.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.5"
    lob_max="0.7"
    speed_min="200"
    speed_max="300"
	friction="1"
    direction_random_rad="0.40"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
    lifetime="100"
    damage="0.2"
	bounce_always="1"
    bounces_left="20"
    bounce_energy="0.5"
    velocity_sets_scale="1"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0.01"
    hit_particle_force_multiplier="0.1"
	velocity_sets_rotation="1"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_small.xml"
    shoot_light_flash_radius="64"
	shoot_light_flash_r="70"
	shoot_light_flash_g="190"
	shoot_light_flash_b="255"
	knockback_force="0.5"
    physics_impulse_coeff="2000"
	>
    <config_explosion
      never_cache="1"
      damage="0"
      camera_shake="0"
      explosion_radius="4"
      explosion_sprite="data/particles/background_cleaner_explosion.xml"
      explosion_sprite_lifetime="0"
      create_cell_probability="0"
      hole_destroy_liquid="1"
      hole_enabled="1"
      ray_energy="400000"
      particle_effect="0"
      damage_mortals="1"
	  physics_explosion_power.min="0.05"
      physics_explosion_power.max="0.1"
      physics_throw_enabled="1"
      shake_vegetation="1"
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

### Key `ProjectileComponent` Attributes:

*   **`lob_min`, `lob_max`**: Controls the minimum and maximum lob angle of the projectile.
*   **`speed_min`, `speed_max`**: Defines the range of initial projectile speeds.
*   **`direction_random_rad`**: Introduces randomness to the projectile's firing direction.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
*   **`lifetime="100"`**: The projectile's lifespan in frames.
*   **`damage="0.2"`**: The base damage dealt by the projectile.
*   **`bounce_always="1"`**: The projectile will always attempt to bounce.
*   **`bounces_left="20"`**: The maximum number of bounces allowed.
*   **`bounce_energy="0.5"`**: The energy retained after each bounce.
*   **`lifetime_randomness="7"`**: Adds variability to the projectile's lifespan.
*   **`muzzle_flash_file`**: Specifies the particle effect for the muzzle flash.
*   **`shoot_light_flash_radius`, `shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: Defines the light flash properties when the projectile is fired.
*   **`knockback_force="0.5"`**: The force applied to knock back entities upon impact.
*   **`physics_impulse_coeff="2000"`**: Coefficient for physics impulse calculations.

#### `config_explosion` Attributes:

*   **`damage="0"`**: The explosion itself does not deal direct damage.
*   **`explosion_radius="4"`**: The radius of the explosion effect.
*   **`hole_destroy_liquid="1"`**: The explosion can destroy liquids.
*   **`hole_enabled="1"`**: The explosion creates holes in terrain.
*   **`ray_energy="400000"`**: The energy of the destructive rays from the explosion.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: Controls the physics force of the explosion.
*   **`stains_enabled="1"`**: The explosion leaves stains on surfaces.

## Sprite Component

This component defines the visual appearance of the projectile.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/background_cleaner.xml"
    rect_animation="fireball"
	emissive="1"
	additive="1"
     >
</SpriteComponent>
```

### Key `SpriteComponent` Attributes:

*   **`image_file`**: Specifies the sprite image used for the projectile.
*   **`rect_animation="fireball"`**: Indicates the sprite uses a "fireball" animation.
*   **`emissive="1"`**: The sprite emits light.
*   **`additive="1"`**: The sprite uses additive blending for rendering.

## Audio Component

This component handles the sound effects associated with the projectile.

```xml
<AudioComponent
      file="data/audio/Desktop/projectiles.bank"
      event_root="player_projectiles/bullet_bubble">
</AudioComponent>
```

### Key `AudioComponent` Attributes:

*   **`file`**: The audio bank file containing the sound events.
*   **`event_root`**: The root event name for player projectile sounds, specifically for the "bullet\_bubble".

## Light Component

This component adds a light source to the projectile.

```xml
<LightComponent
    _enabled="1"
    radius="60"
	fade_out_time="0.1"
	r="10"
	g="40"
	b="80">
</LightComponent>
```

### Key `LightComponent` Attributes:

*   **`radius`**: The radius of the light emitted by the projectile.
*   **`fade_out_time`**: How long it takes for the light to fade out.
*   **`r`, `g`, `b`**: The RGB color values of the light.

## Variable Storage Component

This component stores a variable related to the projectile's own file path.

```xml
<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/bubbleshot.xml"
		>
</VariableStorageComponent>
```

### Key `VariableStorageComponent` Attributes:

*   **`name="projectile_file"`**: The name of the variable being stored.
*   **`value_string`**: The string value assigned to the variable, which is the path to this entity's XML file.