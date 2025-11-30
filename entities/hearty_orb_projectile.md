---
title: Hearty Orb Projectile
category: entities
---

---

# Hearty Orb Projectile

This document details the configuration of the "Hearty Orb" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" 
   >
  <!-- ... other components ... -->
</Entity>
```

## Key Components and Attributes

This section highlights the most important components and their attributes that define the behavior and appearance of the Hearty Orb.

### Base Projectile Configuration

Inherits fundamental projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="0"          <!-- Projectile is not affected by gravity -->
        air_friction="-0.1"    <!-- Slight air resistance -->
        mass="0.05"            <!-- Low mass -->
    >
    </VelocityComponent> 
</Base>
```

### Homing Component

Enables the projectile to track targets.

```xml
<HomingComponent
    target_tag="prey"          <!-- Seeks entities tagged as "prey" -->
    homing_targeting_coeff="10" <!-- Strength of homing behavior -->
    detect_distance="350"      <!-- Range at which it can detect targets -->
    homing_velocity_multiplier="1.0" <!-- Multiplier for homing speed -->
>
</HomingComponent>
```

### Projectile Component

Defines the projectile's core mechanics, including speed, damage, and death behavior.

```xml
<ProjectileComponent 
    _enabled="1" 
    lob_min="0.8"              <!-- Minimum lob angle -->
    lob_max="1.0"              <!-- Maximum lob angle -->
    speed_min="100"            <!-- Minimum projectile speed -->
    speed_max="120"            <!-- Maximum projectile speed -->
    die_on_low_velocity="0"    <!-- Does not die if velocity becomes too low -->
    on_death_explode="1"       <!-- Explodes upon death -->
    on_death_gfx_leave_sprite="0" <!-- Does not leave a sprite graphic on death -->
    on_lifetime_out_explode="1" <!-- Explodes when its lifetime expires -->
    explosion_dont_damage_shooter="1" <!-- The explosion does not harm the entity that fired it -->
    damage="0.3"               <!-- Base damage of the projectile -->
    on_collision_die="1"       <!-- Dies upon collision -->
    lifetime="150"             <!-- Duration in frames before expiring -->
>
    <!-- Explosion configuration -->
    <config_explosion
        never_cache="1" 
        camera_shake="0.5" 
        explosion_radius="1" 
        explosion_sprite="data/particles/explosion_016_plasma_pink.xml" 
        explosion_sprite_lifetime="0.0" 
        create_cell_probability="1" 
        create_cell_material="spark_blue" 
        ray_energy="10000"
        hole_destroy_liquid="1" 
        hole_enabled="1" 
        damage="0.1"               <!-- Damage dealt by the explosion -->
        hole_image="data/temp/explosion_hole.png"
        explosion_sprite_emissive="1"
        explosion_sprite_additive="1"
        particle_effect="0" 
        damage_mortals="1"
        physics_explosion_power.min="0"
        physics_explosion_power.max="0"
        physics_throw_enabled="0"
        shake_vegetation="1"  
        sparks_enabled="1" 
        spark_material="spark_red"
        sparks_count_max="16" 
        sparks_count_min="12"
        light_fade_time="1.2" 
        light_r="180"
        light_g="180"
        light_b="180"
        stains_enabled="1" 
        stains_image="data/temp/explosion_stain.png" 
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
    image_file="data/projectiles_gfx/orb_pink.xml" <!-- Specifies the sprite graphic -->
    offset_x="5" 
    offset_y="5" 
    rect_animation="fireball" <!-- Animation name -->
    emissive="1"              <!-- Sprite is emissive -->
    additive="1"              <!-- Sprite uses additive blending -->
    update_transform_rotation="0"
>
</SpriteComponent>
```

### Light Component

Adds a light source to the projectile.

```xml
<LightComponent 
    _enabled="1" 
    radius="150" 
    r="220"
    g="18"
    b="40">
</LightComponent>
```

### Audio Components

Handles sound effects for the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/magic" >
</AudioComponent>

<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="projectiles/magic_orb/loop"
    auto_play="1">
</AudioLoopComponent>
```

### Hit Effect Component

Specifies an effect to be loaded when the projectile hits something.

```xml
<HitEffectComponent 
    effect_hit="LOAD_CHILD_ENTITY"
    value_string="data/entities/misc/effect_hearty.xml" > <!-- Path to the hit effect entity -->
</HitEffectComponent >
```

### Variable Storage Component

Stores a variable, likely for referencing the projectile's own file.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/orb_hearty.xml"
>
</VariableStorageComponent>
```

### Sprite Particle Emitter Component

Adds a particle effect to the projectile.

```xml
<SpriteParticleEmitterComponent
    sprite_file="data/particles/charm.xml" <!-- Sprite file for particles -->
    delay="0"
    lifetime="1.0"
    color.r="1" color.g="1" color.b="1" color.a="1"
    color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-1"
    velocity.x="0" velocity.y="0"
    gravity.x="0" gravity.y="30"
    velocity_slowdown="0"
    rotation="0"
    angular_velocity="0"
    use_velocity_as_rotation="0"
    scale.x="1" scale.y="1"
    scale_velocity.x="0" scale_velocity.y="0"
    emission_interval_min_frames="1"
    emission_interval_max_frames="2"
    count_min="1" count_max="1"
    randomize_velocity.min_x="-5"
    randomize_velocity.max_x="5"
    randomize_velocity.min_y="-5"
    randomize_velocity.max_y="5"
    randomize_position.min_x="-6"
    randomize_position.max_x="6"
    randomize_position.min_y="-6"
    randomize_position.max_y="6"
>
</SpriteParticleEmitterComponent>
```