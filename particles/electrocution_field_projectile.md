---
title: Electrocution Field Projectile
category: data
---

# Electrocution Field Projectile

This document details the configuration for the Electrocution Field projectile in Noita, designed for AI-assisted modding.

## Core Entity

The base entity defines the projectile's fundamental properties and tags.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
>
  <!-- ... components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Indicates this entity uses default projectile naming conventions.
*   **`tags`**: `projectile_player` - Identifies this as a projectile originating from the player.

## Game Area Effect Component

This component defines the area of effect for the electrocution field.

```xml
<GameAreaEffectComponent
    radius="28"
    frame_length="100"
>
</GameAreaEffectComponent>
```

*   **`radius`**: `28` - The radius of the electrical field in pixels.
*   **`frame_length`**: `100` - The duration of the effect in frames.

## Particle Emitters

Multiple `ParticleEmitterComponent` instances are used to create visual effects for the electrocution field.

### Primary Plasma Emitter

This emitter generates fading plasma particles.

```xml
<ParticleEmitterComponent 
    emitted_material_name="plasma_fading"
    gravity.y="0.0"
    lifetime_min="0.5"
    lifetime_max="1.5"
    count_min="2"
    count_max="4"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.max="28"
    cosmetic_force_create="0"
    airflow_force="1.5"
    airflow_time="0.02"
    airflow_scale="0.05"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    emit_cosmetic_particles="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `plasma_fading` - The material used for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1.5` - The minimum and maximum lifespan of particles in seconds.
*   **`count_min` / `count_max`**: `2` / `4` - The range for the number of particles emitted per burst.
*   **`area_circle_radius.max`**: `28` - The maximum radius for particle emission.
*   **`airflow_force`**: `1.5` - Controls the strength of airflow affecting particles.

### Secondary Plasma Emitter

This emitter also generates plasma particles, with a fixed radius.

```xml
<ParticleEmitterComponent 
    emitted_material_name="plasma_fading"
    gravity.y="0.0"
    lifetime_min="0.5"
    lifetime_max="1.5"
    count_min="4"
    count_max="4"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    area_circle_radius.min="28"
    area_circle_radius.max="28"
    cosmetic_force_create="0"
    airflow_force="0.3"
    airflow_time="0.01"
    airflow_scale="0.05"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    emit_cosmetic_particles="1"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`area_circle_radius.min` / `area_circle_radius.max`**: `28` - Ensures particles are emitted within a precise 28-pixel radius.
*   **`airflow_force`**: `0.3` - A lower airflow force compared to the primary emitter.

### Spark Emitter

This emitter generates blue sparks.

```xml
<ParticleEmitterComponent 
    _tags="enabled_in_world,enabled_in_hand"
    emitted_material_name="spark_blue"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="-24"
    x_pos_offset_max="24"
    y_pos_offset_min="-24"
    y_pos_offset_max="24"
    gravity.y="0"
    x_vel_min="-30"
    x_vel_max="30"
    y_vel_min="-30"
    y_vel_max="30"
    count_min="1"
    count_max="3"
    lifetime_min="0.2"
    lifetime_max="0.3"
    create_real_particles="0"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="10"
    emission_interval_max_frames="25"
    is_emitting="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `spark_blue` - The material for the spark particles.
*   **`x_pos_offset_min` / `x_pos_offset_max`**: `-24` / `24` - Defines the horizontal spread of spark emission.
*   **`y_pos_offset_min` / `y_pos_offset_max`**: `-24` / `24` - Defines the vertical spread of spark emission.
*   **`lifetime_min` / `lifetime_max`**: `0.2` / `0.3` - Short lifespan for sparks.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `10` / `25` - Controls the frequency of spark emissions.

## Base Field Configuration

This section inherits properties from `base_field.xml` and adds specific electrocution effects.

```xml
<Base file="data/entities/projectiles/deck/base_field.xml">
    <SpriteComponent 
        image_file=""
        >
    </SpriteComponent>

    <SpriteParticleEmitterComponent
        sprite_file="data/particles/arc.xml"
        lifetime="0"
        color.r="1" color.g="1" color.b="1" color.a="1"
        color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="0"
        randomize_rotation.min="-3.1415"
        randomize_rotation.max="3.1415"
        randomize_velocity.min_x="-30"
        randomize_velocity.max_x="30"
        randomize_velocity.min_y="-30"
        randomize_velocity.max_y="30"
        >
    </SpriteParticleEmitterComponent>

    <ProjectileComponent 
        damage_game_effect_entities="data/entities/misc/effect_electricity.xml,"
        friendly_fire="1"
        >
        <config_explosion
            explosion_sprite="data/particles/blast_out_electrocution.xml"
            >
        </config_explosion>
    </ProjectileComponent>
    
    <AudioLoopComponent
      file="data/audio/Desktop/projectiles.bank"
      event_name="player_projectiles/field_electric/loop"
      auto_play="1" >
    </AudioLoopComponent>
</Base>
```

*   **`SpriteParticleEmitterComponent`**: Uses `data/particles/arc.xml` for visual arcs, with randomized rotation and velocity.
*   **`ProjectileComponent`**:
    *   **`damage_game_effect_entities`**: `data/entities/misc/effect_electricity.xml` - Applies the electricity effect upon impact or within the field.
    *   **`friendly_fire`**: `1` - Allows the projectile to damage friendly entities.
    *   **`config_explosion`**: `explosion_sprite="data/particles/blast_out_electrocution.xml"` - Defines the visual effect for the explosion.
*   **`AudioLoopComponent`**:
    *   **`event_name`**: `player_projectiles/field_electric/loop` - Plays a looping sound effect for the electrical field.

## Lua Component

This component integrates custom Lua scripting for the projectile's behavior.

```xml
<LuaComponent 
    _enabled="1" 
    script_source_file="data/scripts/projectiles/electrocution_blast.lua" 
    execute_every_n_frame="10"
    >
</LuaComponent>
```

*   **`script_source_file`**: `data/scripts/projectiles/electrocution_blast.lua` - The path to the Lua script that governs the projectile's dynamic behavior.
*   **`execute_every_n_frame`**: `10` - The script will execute every 10 frames.