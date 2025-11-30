---
title: Parallel Alchemist Entity
category: entities
---

# Parallel Alchemist Entity

This document details the configuration for the Parallel Alchemist entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Core Attributes

The Parallel Alchemist is a flying, ranged enemy with unique resistances and attack patterns.

### Base Entity Configuration

```xml
<Entity name="$animal_parallel_alchemist" tags="touchmagic_immunity,polymorphable_NOT">
  <Base file="data/entities/base_enemy_basic.xml" >
    <!-- ... other components ... -->
  </Base>
  <!-- ... other components ... -->
</Entity>
```

*   **`name`**: `$animal_parallel_alchemist` - Unique identifier for the entity.
*   **`tags`**: `touchmagic_immunity`, `polymorphable_NOT` - Grants immunity to touch magic and prevents polymorphing.

## AI and Behavior

The `AnimalAIComponent` governs the Alchemist's movement, detection, and attack capabilities.

### `AnimalAIComponent`

```xml
<AnimalAIComponent 
    preferred_job="JobDefault"
    attack_melee_enabled="0"
    creature_detection_range_x="400"
    creature_detection_range_y="400"
    food_material="blood"
    needs_food="0"
    sense_creatures="1"
    attack_ranged_enabled="1"
    can_fly="1" 
    attack_ranged_entity_file="data/entities/animals/boss_alchemist/wand_orb.xml"
    attack_ranged_action_frame="5"
    attack_ranged_frames_between="180"
    attack_ranged_offset_x="24"
    attack_ranged_offset_y="-24"
    attack_ranged_min_distance="0"
    attack_ranged_max_distance="240"
>
</AnimalAIComponent>
```

*   **`attack_melee_enabled`**: `0` - The Alchemist does not perform melee attacks.
*   **`creature_detection_range_x` / `creature_detection_range_y`**: `400` - Range at which the Alchemist detects other creatures.
*   **`sense_creatures`**: `1` - Enables creature sensing.
*   **`attack_ranged_enabled`**: `1` - Enables ranged attacks.
*   **`can_fly`**: `1` - Allows the Alchemist to fly.
*   **`attack_ranged_entity_file`**: `data/entities/animals/boss_alchemist/wand_orb.xml` - Specifies the projectile entity used for ranged attacks.
*   **`attack_ranged_frames_between`**: `180` - Cooldown in frames between ranged attacks.
*   **`attack_ranged_max_distance`**: `240` - Maximum distance for ranged attacks.

## Damage and Resistances

The `DamageModelComponent` defines the Alchemist's health and how it takes damage.

### `DamageModelComponent`

```xml
<DamageModelComponent 
    hp="40"
    blood_material="slime"
    blood_sprite_directional="data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml"
    blood_sprite_large="data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml"
    ragdoll_material="rock_static_glow"
    critical_damage_resistance="0.8"
    physics_objects_damage="0"
    air_needed="0" 
>
    <damage_multipliers
        projectile="0.3"
        electricity="0.6"
        fire="0.4"
    >
    </damage_multipliers>
</DamageModelComponent>
```

*   **`hp`**: `40` - The Alchemist's health points.
*   **`blood_material`**: `slime` - The material of the blood it spills.
*   **`critical_damage_resistance`**: `0.8` - High resistance to critical damage.
*   **`damage_multipliers`**:
    *   `projectile`: `0.3` - Takes significantly reduced damage from projectiles.
    *   `electricity`: `0.6` - Takes reduced damage from electricity.
    *   `fire`: `0.4` - Takes reduced damage from fire.

## Visuals and Physics

### `SpriteComponent`

```xml
<SpriteComponent 
    image_file="data/entities/animals/parallel/alchemist/sprite.xml" 
    offset_x="0"
    offset_y="0">
</SpriteComponent>
```

*   **`image_file`**: `data/entities/animals/parallel/alchemist/sprite.xml` - Path to the sprite definition.

### `PathFindingComponent`

```xml
<PathFindingComponent
    can_jump="0" 
    can_walk="0"
    can_fly="1"
>
</PathFindingComponent>
```

*   **`can_fly`**: `1` - Confirms the entity's ability to fly.

### `HitboxComponent`

```xml
<HitboxComponent 
    _enabled="1" 
    aabb_max_x="16" 
    aabb_max_y="12" 
    aabb_min_x="-16" 
    aabb_min_y="-50" >
</HitboxComponent>
```

*   Defines the bounding box for hit detection.

### `CharacterDataComponent`

```xml
<CharacterDataComponent
    collision_aabb_min_x="-16.0" 
    collision_aabb_max_x="16.0" 
    collision_aabb_min_y="-50" 
    collision_aabb_max_y="14"
    mass="1.8" >
</CharacterDataComponent>
```

*   Defines collision boundaries and mass.

## Audio

The Alchemist has distinct audio cues for movement and general sounds.

### `AudioLoopComponent`

```xml
<AudioLoopComponent
    file="data/audio/Desktop/animals.bank"
    event_name="animals/enlightened_alchemist/movement_loop"
    set_speed_parameter="1"
    auto_play="1">
</AudioLoopComponent>
```

*   **`event_name`**: `animals/enlightened_alchemist/movement_loop` - Plays a looping sound during movement.

### `AudioComponent`

```xml
<AudioComponent
    file="data/audio/Desktop/animals.bank"
    event_root="animals/enlightened_alchemist" >
</AudioComponent>
```

*   **`event_root`**: `animals/enlightened_alchemist` - Base event for other sounds associated with the Alchemist.

## Particle Effects

The Alchemist emits smoke and slime particles.

### `ParticleEmitterComponent` (Smoke)

```xml
<ParticleEmitterComponent 
    emitted_material_name="smoke"
    gravity.y="-19"
    x_vel_min="-5"
    x_vel_max="5"
    y_vel_min="0"
    y_vel_max="50"
    x_pos_offset_min="-6"
    x_pos_offset_max="6"
    y_pos_offset_min="-20"
    y_pos_offset_max="1"
    friction="1"
    count_min="1"
    count_max="4"
    lifetime_min="2"
    lifetime_max="20"
    create_real_particles="0"
    render_on_grid="1"
    airflow_force="0.3"
    emission_interval_min_frames="1"
    emission_interval_max_frames="16"
    is_emitting="1"
>
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `smoke` - The type of particle emitted.
*   **`emission_interval_max_frames`**: `16` - Controls the frequency of smoke emission.

### `ParticleEmitterComponent` (Slime)

```xml
<ParticleEmitterComponent 
    emitted_material_name="slime"
    delay_frames="0"
    x_pos_offset_min="-8"
    x_pos_offset_max="8"
    y_pos_offset_min="-20"
    y_pos_offset_max="1"
    count_min="1"
    count_max="1"
    lifetime_min="5"
    lifetime_max="20"
    create_real_particles="1"
    emission_interval_min_frames="5"
    emission_interval_max_frames="60"
    is_emitting="1"
>
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `slime` - The type of particle emitted.
*   **`create_real_particles`**: `1` - Emits actual slime particles.

## Lua Scripting

The Alchemist utilizes Lua scripts for managing projectile counts and damage reception.

### `LuaComponent` (Projectile Counter)

```xml
<LuaComponent
    _tags="counter"
    script_source_file="data/entities/animals/boss_alchemist/projectile_counter_create.lua"
    execute_every_n_frame="10"
>
</LuaComponent>
```

*   **`script_source_file`**: `data/entities/animals/boss_alchemist/projectile_counter_create.lua` - Script for managing projectile creation.
*   **`execute_every_n_frame`**: `10` - Executes the script every 10 frames.

### `LuaComponent` (Damage Counter)

```xml
<LuaComponent
    script_damage_received="data/entities/animals/boss_alchemist/projectile_counter_create_damage.lua"
    execute_every_n_frame="-1"
>
</LuaComponent>
```

*   **`script_damage_received`**: `data/entities/animals/boss_alchemist/projectile_counter_create_damage.lua` - Script for handling damage reception.

## Status Effect Immunities

The Alchemist is immune to freeze and electricity.

### `Entity` (Freeze Immunity)

```xml
<Entity>
    <InheritTransformComponent />
    <GameEffectComponent 
        effect="PROTECTION_FREEZE"
        frames="-1"
    >
    </GameEffectComponent >
</Entity>
```

### `Entity` (Electricity Immunity)

```xml
<Entity>
    <InheritTransformComponent />
    <GameEffectComponent 
        effect="PROTECTION_ELECTRICITY"
        frames="-1"
    >
    </GameEffectComponent >
</Entity>
```