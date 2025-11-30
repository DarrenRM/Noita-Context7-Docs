---
title: Darkflame Stationary Projectile
category: entities
---

# Darkflame Stationary Projectile

This document details the configuration of the "darkflame_stationary" projectile entity in Noita, focusing on its properties and behaviors relevant to AI-assisted modding.

## Entity Definition

The core of this entity is a projectile with specific characteristics, designed to remain stationary upon creation and explode after a set duration or on collision.

```xml
<Entity
  name="$projectile_default"
>
  <!-- ... other components ... -->
</Entity>
```

## Key Components and Attributes

### Base Projectile Configuration

This section inherits fundamental projectile properties.

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
    gravity_y="0"       <!-- No vertical gravity applied -->
    air_friction="0"    <!-- No air resistance -->
    mass="0.03"         <!-- Small mass -->
  >
  </VelocityComponent>
</Base>
```

### Projectile Component

This is the primary component defining the projectile's behavior.

```xml
<ProjectileComponent
  _enabled="1"
  speed_min="0"       <!-- Minimum initial speed -->
  speed_max="0"       <!-- Maximum initial speed (results in stationary projectile) -->
  die_on_low_velocity="0" <!-- Does not die if velocity becomes low -->
  on_death_explode="1"    <!-- Explodes when it dies -->
  on_death_gfx_leave_sprite="0" <!-- Does not leave sprite on death -->
  on_lifetime_out_explode="1" <!-- Explodes when lifetime expires -->
  explosion_dont_damage_shooter="1" <!-- Shooter is immune to the explosion -->
  damage="0.25"       <!-- Base damage value -->
  on_collision_die="1"    <!-- Dies upon collision -->
  lifetime="90"       <!-- Duration in frames before exploding -->
>
  <damage_by_type
    fire="0.25"       <!-- Damage type specific to fire -->
  >
  </damage_by_type>
  <config_explosion
    never_cache="1"
    camera_shake="0"
    damage="0"          <!-- Explosion itself deals no direct damage -->
    explosion_radius="1"
    explosion_sprite="data/particles/darkflame.xml" <!-- Visual effect of the explosion -->
    explosion_sprite_random_rotation="0"
    explosion_sprite_lifetime="0"
    create_cell_probability="0"
    ray_energy="0"
    hole_destroy_liquid="0"
    hole_enabled="0"
    particle_effect="0"
    damage_mortals="0"
    physics_explosion_power.min="0"
    physics_explosion_power.max="0"
    physics_throw_enabled="0"
    shake_vegetation="0"
    sparks_enabled="0"
    light_fade_time="0.1"
    light_enabled="1"   <!-- Enables light emission -->
    light_r="80"        <!-- Red component of light -->
    light_g="5"         <!-- Green component of light -->
    light_b="120"       <!-- Blue component of light -->
    light_radius_coeff="64" <!-- Radius multiplier for light -->
    stains_enabled="0"
  >
  </config_explosion>
</ProjectileComponent>
```

### Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent
  _enabled="1"
  alpha="1"
  image_file="data/projectiles_gfx/darkflame.xml" <!-- Path to the sprite's graphical definition -->
  offset_x="6"
  offset_y="6"
  rect_animation="spawn" <!-- Specifies the animation state -->
>
</SpriteComponent>
```

### Light Component

Adds a light source to the projectile.

```xml
<LightComponent
  _enabled="1"
  radius="64"
  r="80"
  g="5"
  b="120"
  fade_out_time="0.3"
>
</LightComponent>
```

### Variable Storage Component

Stores a reference to the projectile's own XML file.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/darkflame_stationary.xml"
>
</VariableStorageComponent>
```