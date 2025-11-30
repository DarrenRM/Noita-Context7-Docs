---
title: Radioactive Blob Trail Projectile
category: entities
---

# Radioactive Blob Trail Projectile

This document details the configuration of the `radioactive_blob_trail.xml` entity, which defines a projectile that leaves a trail of radioactive liquid.

## Core Entity

The entity is tagged as `hittable` and uses `$projectile_default` as its base name, indicating it inherits common projectile properties.

```xml
<Entity tags="hittable" name="$projectile_default">
    <!-- ... other components ... -->
</Entity>
```

## Base Projectile Properties

Inherits from `base_projectile.xml`, with specific velocity and physics configurations.

### VelocityComponent

*   **gravity_y**: `10` - Applies downward gravitational pull.
*   **air_friction**: `0` - No air resistance.
*   **mass**: `0.055` - Light mass.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="10"
        air_friction="0"
        mass="0.055"
        >
    </VelocityComponent>
</Base>
```

## Projectile Component

Defines the behavior and effects of the projectile.

### ProjectileComponent

*   **speed_min/max**: `90`/`115` - The projectile's speed range.
*   **on\_death\_explode**: `1` - Explodes upon death.
*   **on\_lifetime\_out\_explode**: `1` - Explodes when its lifetime expires.
*   **on\_collision\_die**: `1` - Dies upon collision.
*   **damage**: `0.25` - Base damage dealt by the projectile.
*   **lifetime**: `330` - Duration in frames before expiring.
*   **shoot\_light\_flash\_radius**: `72` - Radius of the light flash when shot.
*   **knockback\_force**: `1.5` - Force applied to knock back entities.

#### config\_explosion

Details the explosion properties when the projectile dies or its lifetime ends.

*   **damage**: `0.3` - Damage dealt by the explosion.
*   **camera\_shake**: `3.5` - Intensity of camera shake during explosion.
*   **explosion\_radius**: `9` - The radius of the explosion.
*   **create\_cell\_probability**: `5` - Chance to create radioactive liquid cells.
*   **create\_cell\_material**: `radioactive_liquid_fading` - The material of the created cells.
*   **hole\_enabled**: `1` - Creates holes in terrain.
*   **hole\_image**: `data/temp/explosion_hole.png` - The image used for holes.
*   **physics\_explosion\_power.min/max**: `0.2`/`0.3` - Minimum and maximum physics force applied by the explosion.
*   **stains\_enabled**: `1` - Leaves stains on surfaces.
*   **stains\_radius**: `9` - Radius of the stains.

```xml
<ProjectileComponent
    _enabled="1"
    speed_min="90"
    speed_max="115"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    on_collision_die="1"
    damage="0.25"
    lifetime="330"
    shoot_light_flash_r="40"
    shoot_light_flash_g="120"
    shoot_light_flash_b="20"
    shoot_light_flash_radius="72"
    knockback_force="1.5"
    >
    <config_explosion
        never_cache="1"
        damage="0.3"
        camera_shake="3.5"
        explosion_radius="9"
        explosion_sprite="data/particles/explosion_032_slimeburst.xml"
        explosion_sprite_lifetime="0"
        create_cell_probability="5"
        create_cell_material="radioactive_liquid_fading"
        hole_destroy_liquid="0"
        hole_enabled="1"
        hole_image="data/temp/explosion_hole.png"
        particle_effect="0"
        damage_mortals="1"
        physics_explosion_power.min="0.2"
        physics_explosion_power.max="0.3"
        physics_throw_enabled="1"
        shake_vegetation="1"
        sparks_count_max="20"
        sparks_count_min="7"
        sparks_enabled="0"
        stains_enabled="1"
        stains_radius="9"
        audio_enabled="0" >
    </config_explosion>
</ProjectileComponent>
```

## Visuals

### SpriteComponent

Defines the visual appearance of the projectile.

*   **image\_file**: `data/projectiles_gfx/slime.xml` - The sprite asset used.
*   **offset\_x/y**: `8`/`6` - Offset for sprite positioning.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/slime.xml"
    next_rect_animation=""
    offset_x="8"
    offset_y="6"
    rect_animation=""
    >
</SpriteComponent>
```

### ParticleEmitterComponent

Responsible for creating the radioactive trail.

*   **emitted\_material\_name**: `radioactive_liquid` - The material emitted.
*   **count\_min/max**: `1`/`2` - Number of particles emitted per emission.
*   **is\_trail**: `1` - Indicates this emitter creates a trail.
*   **trail\_gap**: `2.5` - Spacing between trail particles.
*   **lifetime\_min/max**: `0.1`/`1.3` - Lifetime of emitted particles.
*   **emit\_real\_particles**: `1` - Emits actual game particles.
*   **emission\_interval\_min/max\_frames**: `1`/`1` - Emits particles every frame.

```xml
<ParticleEmitterComponent
    emitted_material_name="radioactive_liquid"
    count_min="1"
    count_max="2"
    offset.x="-1"
    offset.y="0"
    x_pos_offset_min="-1"
    y_pos_offset_min="-2"
    x_pos_offset_max="1"
    y_pos_offset_max="2"
    count_min="1"
    count_max="1"
    is_trail="1"
    trail_gap="2.5"
    lifetime_min="0.1"
    lifetime_max="1.3"
    render_on_grid="1"
    create_real_particles="0"
    emit_cosmetic_particles="0"
    emit_real_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

### LightComponent

Adds a light source to the projectile.

*   **radius**: `30` - The radius of the light.
*   **r/g/b**: `99`/`205`/`139` - The color of the light (greenish hue).

```xml
<LightComponent
    _enabled="1"
    radius="30"
    r="99"
    g="205"
    b="139"
    offset_y="0"
    >
</LightComponent>
```

## Damage and Health

### DamageModelComponent

Defines the health and damage-related properties of the projectile.

*   **hp**: `0.2` - Health points of the projectile.
*   **blood\_material**: `radioactive_liquid_fading` - The material created when damaged (if applicable).

```xml
<DamageModelComponent
    _enabled="1"
    hp="0.2"
    fire_probability_of_ignition="0"
    falling_damages="0"
    air_needed="0"
    materials_damage="0"
    ragdoll_filenames_file=""
    blood_material="radioactive_liquid_fading"
    blood_multiplier="0"
    create_ragdoll="0" >
</DamageModelComponent>
```

## Audio

### AudioComponent

Specifies the sound effects associated with the projectile.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank file.
*   **event\_root**: `projectiles/slime` - The root event for projectile sounds.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/slime">
</AudioComponent>
```

## Variables

### VariableStorageComponent

Stores variables related to the projectile.

*   **name**: `projectile_file`
*   **value\_string**: `data/entities/projectiles/radioactive_blob_trail.xml` - Self-reference to its own file path.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/radioactive_blob_trail.xml"
    >
</VariableStorageComponent>
```