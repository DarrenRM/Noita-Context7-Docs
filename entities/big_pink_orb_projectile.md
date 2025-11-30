---
title: Big Pink Orb Projectile
category: entities
---

# Big Pink Orb Projectile

This document details the configuration for the "Big Pink Orb" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity definition for the Big Pink Orb.

```xml
<Entity 
  name="$projectile_default" 
  tags="resist_repulsion"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Inherits default projectile naming.
*   **`tags`**: `resist_repulsion` - Indicates resistance to repulsion forces.

## Base Projectile Configuration

Inherits fundamental projectile properties from `base_projectile.xml`.

```xml
<Base file="data/entities/base_projectile.xml">
    <VelocityComponent
        gravity_y="0"
        air_friction="0"
        mass="0.8"
    >
    </VelocityComponent>
</Base>
```

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: No vertical gravity applied.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.8"`: Defines the projectile's mass.

## Projectile Behavior

Defines the specific characteristics and actions of the Big Pink Orb.

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
    lifetime="100" 
    knockback_force="2.0"
>
    <!-- ... config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min`, `lob_max`**: Controls the projectile's lobbing behavior (0.8 to 1.0).
*   **`speed_min`, `speed_max`**: Sets the projectile's speed range (100 to 120).
*   **`die_on_low_velocity`**: `0` - Does not die when velocity is low.
*   **`on_death_explode`**: `1` - Explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion will not damage the entity that fired it.
*   **`damage`**: `0.8` - Base damage dealt by the projectile.
*   **`on_collision_die`**: `1` - The projectile dies upon collision.
*   **`lifetime`**: `100` - The projectile exists for 100 frames.
*   **`knockback_force`**: `2.0` - The force applied for knockback on collision.

### Explosion Configuration

Details the effects of the projectile's explosion.

```xml
<config_explosion
    never_cache="1" 
    camera_shake="4.0" 
    explosion_radius="20" 
    explosion_sprite="data/particles/explosion_032.xml" 
    explosion_sprite_lifetime="0.0" 
    create_cell_probability="1" 
    create_cell_material="plasma_fading_pink" 
    ray_energy="10000"
    hole_destroy_liquid="1" 
    hole_enabled="1" 
    damage="0.5"
    hole_image="data/temp/explosion_hole.png"
    explosion_sprite_emissive="0"
    explosion_sprite_additive="1"
    particle_effect="0" 
    damage_mortals="1"
    physics_explosion_power.min="0.4" 
    physics_explosion_power.max="0.6"
    physics_throw_enabled="1"
    shake_vegetation="1"  
    sparks_enabled="1" 
    sparks_count_max="8" 
    sparks_count_min="4"
    spark_material="plasma_fading_pink"
    light_fade_time="1.2" 
    light_r="155"
    light_g="15"
    light_b="140"
    stains_enabled="1" 
    stains_image="data/temp/explosion_stain.png"
    audio_enabled="0" 
>
</config_explosion>
```

*   **`camera_shake`**: `4.0` - Intensity of camera shake on explosion.
*   **`explosion_radius`**: `20` - The radius of the explosion effect.
*   **`explosion_sprite`**: `data/particles/explosion_032.xml` - Visual effect for the explosion.
*   **`create_cell_probability`**: `1` - Always creates a cell upon explosion.
*   **`create_cell_material`**: `plasma_fading_pink` - The material of the created cell.
*   **`ray_energy`**: `10000` - Energy value for potential ray interactions.
*   **`hole_destroy_liquid`**: `1` - Destroys liquids in its path.
*   **`hole_enabled`**: `1` - Creates holes in terrain.
*   **`damage`**: `0.5` - Damage dealt by the explosion itself.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `0.4` to `0.6` - Controls the physics force of the explosion.
*   **`sparks_enabled`**: `1` - Sparks are generated.
*   **`spark_material`**: `plasma_fading_pink` - Material of the sparks.
*   **`light_r`, `light_g`, `light_b`**: `155`, `15`, `140` - RGB values for the explosion's light.

## Visual Representation

Defines the sprite and animation for the projectile.

```xml
<SpriteComponent 
    _enabled="1" 
    alpha="1" 
    image_file="data/projectiles_gfx/orb_pink_big.xml" 
    rect_animation="fireball" 
    additive="1"
>
</SpriteComponent>
```

*   **`image_file`**: `data/projectiles_gfx/orb_pink_big.xml` - Path to the sprite's graphical definition.
*   **`rect_animation`**: `fireball` - Specifies the animation to use.
*   **`additive`**: `1` - Uses additive blending for the sprite.

## Particle Emitter

Configures a particle emitter attached to the projectile.

```xml
<SpriteParticleEmitterComponent
    sprite_file="data/particles/orb_pink_big_out.xml"
    delay="0"
    lifetime="0"
    additive="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    count_min="1" count_max="1"
    randomize_rotation.min="-0.3415"
    randomize_rotation.max="0.3415"
    randomize_angular_velocity.min="-1.3415"
    randomize_angular_velocity.max="1.3415"
    is_emitting="1"
>
</SpriteParticleEmitterComponent>
```

*   **`sprite_file`**: `data/particles/orb_pink_big_out.xml` - The sprite definition for the emitted particles.
*   **`is_emitting`**: `1` - The emitter is active.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1` - Particles are emitted every frame.
*   **`count_min`, `count_max`**: `1` - Emits one particle per emission.

## Lighting Component

Adds a light source to the projectile.

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
*   **`r`, `g`, `b`**: `150`, `35`, `120` - RGB color values for the light.

## Audio Component

Specifies the sound bank and event root for projectile audio.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/orb_b" >
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **`event_root`**: `projectiles/orb_b` - The root event for projectile sounds.

## Variable Storage

Stores the projectile's own file path for potential referencing.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/orb_pink_big.xml"
>
</VariableStorageComponent>
```

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/orb_pink_big.xml` - The value stored, which is the path to this entity's XML file.