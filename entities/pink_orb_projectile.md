---
title: Pink Orb Projectile
category: entities
---

# Pink Orb Projectile

This document details the configuration of the "Pink Orb" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag, with specific attributes and components dictating its behavior and appearance.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Indicates this entity uses a default projectile naming convention.
*   **`tags`**: `projectile_player` - Identifies this projectile as originating from the player.

## Key Components

### Base Projectile (`<Base>`)

This component inherits fundamental projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="0"
        air_friction="0"
        mass="0.08"
        >
    </VelocityComponent> 
</Base>
```

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity in the Y-axis.
    *   `air_friction="0"`: No air friction is applied.
    *   `mass="0.08"`: A small mass value.

### Homing (`<HomingComponent>`)

Enables the projectile to track targets.

```xml
<HomingComponent
    target_tag="homing_target"
    homing_targeting_coeff="5"
    detect_distance="350"
    homing_velocity_multiplier="1.0"
    >
</HomingComponent>
```

*   **`target_tag`**: `homing_target` - The tag that targets must possess to be acquired.
*   **`homing_targeting_coeff`**: `5` - Controls the strength of the homing behavior.
*   **`detect_distance`**: `350` - The maximum distance at which targets can be detected.

### Projectile Behavior (`<ProjectileComponent>`)

This is the primary component defining the projectile's offensive and destructive capabilities.

```xml
<ProjectileComponent 
    _enabled="1" 
    lob_min="0.8"
    lob_max="1.0"
    speed_min="100"
    speed_max="120"
    die_on_low_velocity="0"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0" 
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    damage="0.8"
    on_collision_die="1"
    direction_random_rad="0.65"
    lifetime="100"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_small_pink.xml"
    shoot_light_flash_r="255"
    shoot_light_flash_g="160"
    shoot_light_flash_b="245"
    shoot_light_flash_radius="180"
    knockback_force="1.6"
    >
    <!-- ... config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Defines the minimum and maximum lob (arc) of the projectile.
*   **`speed_min` / `speed_max`**: `100` / `120` - The projectile's speed range.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`damage`**: `0.8` - The base damage dealt by the projectile.
*   **`lifetime`**: `100` - The duration in frames before the projectile expires.
*   **`knockback_force`**: `1.6` - The force applied for knockback on collision.
*   **`muzzle_flash_file`**: Specifies the particle effect for the muzzle flash.
*   **`shoot_light_flash_*`**: Defines the color and radius of the light flash when shot.

#### Explosion Configuration (`<config_explosion>`)

Details the effects of the projectile's explosion.

```xml
<config_explosion
    never_cache="1" 
    camera_shake="0" 
    explosion_radius="20" 
    explosion_sprite="data/particles/explosion_032_pink.xml" 
    create_cell_probability="1" 
    create_cell_material="plasma_fading"
    ray_energy="100000"
    hole_destroy_liquid="1" 
    hole_enabled="1" 
    damage="0.5"
    physics_explosion_power.min="0.3"
    physics_explosion_power.max="0.5"
    physics_throw_enabled="1"
    sparks_enabled="1" 
    spark_material="plasma_fading_pink"
    sparks_count_min="12"
    sparks_count_max="16" 
    light_r="155"
    light_g="15"
    light_b="140"
    stains_enabled="1" 
    >
</config_explosion>
```

*   **`explosion_radius`**: `20` - The radius of the explosion.
*   **`explosion_sprite`**: The visual effect for the explosion.
*   **`create_cell_material`**: `plasma_fading` - The material of cells created by the explosion.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`damage`**: `0.5` - Damage dealt by the explosion itself.
*   **`physics_explosion_power.min` / `max`**: `0.3` / `0.5` - Controls the physics force of the explosion.
*   **`sparks_enabled`**: `1` - Enables spark effects.
*   **`spark_material`**: `plasma_fading_pink` - The material of the sparks.
*   **`light_*`**: Defines the color of the light emitted by the explosion.
*   **`stains_enabled`**: `1` - Enables the creation of impact stains.

### Visuals (`<SpriteComponent>`)

Defines the projectile's visual appearance.

```xml
<SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/orb_pink_big.xml" 
    offset_x="8" 
    offset_y="8" 
    rect_animation="fireball" 
    emissive="1"
    additive="1"
    >
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/orb_pink_big.xml` - The sprite asset used for the projectile.
*   **`offset_x` / `offset_y`**: `8` / `8` - Offsets for sprite positioning.
*   **`rect_animation`**: `fireball` - Specifies a rectangle animation.
*   **`emissive` / `additive`**: `1` - Indicates the sprite uses emissive and additive blending.

### Particle Emitter (`<SpriteParticleEmitterComponent>`)

Manages particle effects associated with the projectile.

```xml
<SpriteParticleEmitterComponent
    sprite_file="data/particles/orb_pink_big_out.xml"
    delay="0"
    lifetime="0"
    additive="1"
    emissive="1"
    count_min="1" count_max="1"
    randomize_rotation.min="-0.3415"
    randomize_rotation.max="0.3415"
    randomize_angular_velocity.min="-1.3415"
    randomize_angular_velocity.max="1.3415"
    is_emitting="1"
    >
</SpriteParticleEmitterComponent>
```

*   **`sprite_file`**: `data/particles/orb_pink_big_out.xml` - The particle sprite asset.
*   **`additive` / `emissive`**: `1` - Particle blending modes.
*   **`count_min` / `max`**: `1` / `1` - Number of particles emitted.
*   **`randomize_rotation` / `angular_velocity`**: Controls random rotation and angular velocity of emitted particles.

### Light (`<LightComponent>`)

Defines the light emitted by the projectile.

```xml
<LightComponent 
    _enabled="1" 
    radius="150" 
    r="150"
    g="35"
    b="120">
</LightComponent>
```

*   **`radius`**: `150` - The radius of the light.
*   **`r` / `g` / `b`**: `150` / `35` / `120` - The RGB color values of the light.

### Variable Storage (`<VariableStorageComponent>`)

Stores variables associated with the entity.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/pink_orb.xml"
    >
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/pink_orb.xml` - The string value, likely referencing its own file path.