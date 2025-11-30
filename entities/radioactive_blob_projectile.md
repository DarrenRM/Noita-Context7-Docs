---
title: Radioactive Blob Projectile
category: entities
---

# Radioactive Blob Projectile

This document details the configuration for the `radioactive_blob.xml` projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity is a `hittable` projectile with the default name `$projectile_default`.

```xml
<Entity tags="hittable" name="$projectile_default">
    <!-- ... -->
</Entity>
```

## Base Projectile Configuration

Inherits from `base_projectile.xml` with specific physics properties.

### VelocityComponent

*   **gravity_y**: `10` - Controls the downward acceleration due to gravity.
*   **air_friction**: `0` - No air resistance.
*   **mass**: `0.055` - The projectile's mass.

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

Defines the projectile's behavior and effects.

### ProjectileComponent

*   **speed\_min**: `90` - Minimum projectile speed.
*   **speed\_max**: `105` - Maximum projectile speed.
*   **on\_death\_explode**: `1` - The projectile explodes upon death.
*   **on\_death\_gfx\_leave\_sprite**: `0` - No sprite is left behind on death.
*   **on\_lifetime\_out\_explode**: `1` - Explodes when its lifetime expires.
*   **on\_collision\_die**: `1` - Dies upon collision.
*   **damage**: `0.25` - Base damage dealt by the projectile.
*   **lifetime**: `330` - Duration in frames before expiring.
*   **shoot\_light\_flash\_r/g/b**: `40/120/20` - RGB values for the light flash when shot.
*   **shoot\_light\_flash\_radius**: `72` - Radius of the light flash.
*   **knockback\_force**: `1.5` - Force applied to knock back entities.

#### config\_explosion

Nested configuration for the explosion effect.

*   **never\_cache**: `1` - Prevents caching of the explosion.
*   **damage**: `0.3` - Damage dealt by the explosion.
*   **camera\_shake**: `3.5` - Intensity of camera shake on explosion.
*   **explosion\_radius**: `9` - Radius of the explosion.
*   **explosion\_sprite**: `data/particles/explosion_032_slimeburst.xml` - GFX for the explosion.
*   **create\_cell\_probability**: `5` - Chance to create a liquid cell.
*   **create\_cell\_material**: `radioactive_liquid_fading` - Material of the created liquid cell.
*   **hole\_enabled**: `1` - Creates a hole on impact.
*   **hole\_image**: `data/temp/explosion_hole.png` - Image used for the hole.
*   **damage\_mortals**: `1` - The explosion damages living entities.
*   **physics\_explosion\_power.min/max**: `0.2/0.3` - Minimum/maximum physics force applied by the explosion.
*   **shake\_vegetation**: `1` - Shakes vegetation in the explosion radius.
*   **sparks\_count\_min/max**: `7/20` - Range for the number of sparks.
*   **stains\_enabled**: `1` - Creates stains on surfaces.
*   **stains\_radius**: `9` - Radius of the stains.
*   **audio\_enabled**: `0` - Explosion sound is disabled here (handled by AudioComponent).

```xml
<ProjectileComponent
    _enabled="1"
    speed_min="90"
    speed_max="105"
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

*   **image\_file**: `data/projectiles_gfx/slime.xml` - The sprite asset used for the projectile.
*   **offset\_x/y**: `8/6` - Offset for the sprite's position.

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

Emits cosmetic particles to create a trail effect.

*   **emitted\_material\_name**: `radioactive_liquid_fading` - The material of the emitted particles.
*   **count\_min/max**: `1/2` - Number of particles emitted per emission.
*   **is\_trail**: `1` - Enables trail emission.
*   **trail\_gap**: `2.5` - Spacing between trail particles.
*   **lifetime\_min/max**: `0.1/1.3` - Lifetime of emitted particles.
*   **emit\_cosmetic\_particles**: `1` - Ensures particles are cosmetic.
*   **is\_emitting**: `1` - The emitter is active.

```xml
<ParticleEmitterComponent
    emitted_material_name="radioactive_liquid_fading"
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
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

### LightComponent

Adds a light source to the projectile.

*   **radius**: `30` - The radius of the light.
*   **r/g/b**: `99/205/139` - RGB color of the light.

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

Defines the projectile's health and how it interacts with damage.

*   **hp**: `0.2` - Health points of the projectile.
*   **blood\_material**: `radioactive_liquid_fading` - The material that acts as "blood" when damaged.

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

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing projectile sounds.
*   **event\_root**: `projectiles/slime` - The root event for slime-related projectile sounds.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/slime">
</AudioComponent>
```

## Variables

### VariableStorageComponent

Stores variables associated with the entity.

*   **name**: `projectile_file`
*   **value\_string**: `data/entities/projectiles/radioactive_blob.xml` - Path to this entity's XML file.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/radioactive_blob.xml"
    >
</VariableStorageComponent>
```