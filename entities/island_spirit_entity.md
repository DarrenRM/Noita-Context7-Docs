---
title: Island Spirit Entity
category: entities
---

# Island Spirit Entity

This document details the configuration of the Island Spirit entity in Noita, focusing on its attributes and behaviors relevant to AI-assisted modding.

## Core Attributes

The Island Spirit is a boss-type enemy with unique movement and attack patterns.

```xml
<Entity name="$animal_islandspirit" tags="touchmagic_immunity,polymorphable_NOT,boss,miniboss,music_energy_100,necrobot_NOT,glue_NOT,curse_NOT,islandspirit">
```

*   **`name`**: `$animal_islandspirit` - Internal identifier for the entity.
*   **`tags`**: A comprehensive list of tags defining its properties and interactions:
    *   `touchmagic_immunity`: Immune to Touch Magic.
    *   `polymorphable_NOT`: Cannot be polymorphed.
    *   `boss`, `miniboss`: Identifies it as a significant enemy.
    *   `music_energy_100`: Likely related to music or ambient effects.
    *   `necrobot_NOT`, `glue_NOT`, `curse_NOT`: Not affected by these specific status effects.
    *   `islandspirit`: A unique tag for this entity.

## Base Enemy Configuration

The Island Spirit inherits from `base_enemy_basic.xml`, providing fundamental enemy functionalities.

```xml
<Base file="data/entities/base_enemy_basic.xml" >
    <ItemChestComponent level="2" />
    <!-- ... other components ... -->
</Base>
```

*   **`ItemChestComponent level="2"`**: Indicates it drops loot of level 2 rarity.

### Animal AI Component

This component governs the creature's behavior, detection, and combat.

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
    attack_ranged_entity_file="data/entities/animals/boss_spirit/orb.xml"
    attack_ranged_action_frame="5"
    attack_ranged_frames_between="240"
    attack_ranged_offset_x="8"
    attack_ranged_offset_y="-12"
    attack_ranged_min_distance="0"
    attack_ranged_max_distance="240"
>
</AnimalAIComponent>
```

*   **`attack_melee_enabled="0"`**: The Island Spirit does not use melee attacks.
*   **`creature_detection_range_x="400"`, `creature_detection_range_y="400"`**: Detects creatures within a 400-unit radius.
*   **`sense_creatures="1"`**: Actively senses other creatures.
*   **`attack_ranged_enabled="1"`**: Capable of ranged attacks.
*   **`can_fly="1"`**: Can fly.
*   **`attack_ranged_entity_file="data/entities/animals/boss_spirit/orb.xml"`**: The projectile used for ranged attacks is defined in `orb.xml`.
*   **`attack_ranged_frames_between="240"`**: Ranged attacks occur every 240 frames.

### Damage Model Component

Defines the entity's health, resistances, and damage-related properties.

```xml
<DamageModelComponent
    hp="40"
    blood_material="spark_blue"
    blood_spray_material="spark_blue"
    fire_probability_of_ignition="0"
    ragdoll_material="spark_blue"
    air_needed="0"
>
    <damage_multipliers
        slice="0.0"
        projectile="0.3"
        electricity="0.6"
        fire="0.4"
        holy="0"
    >
    </damage_multipliers>
</DamageModelComponent>
```

*   **`hp="40"`**: The Island Spirit has 40 hit points.
*   **`blood_material="spark_blue"`**: Its blood is represented by blue sparks.
*   **`damage_multipliers`**:
    *   `slice="0.0"`: Immune to slice damage.
    *   `projectile="0.3"`: Takes 30% damage from projectiles.
    *   `electricity="0.6"`: Takes 60% damage from electricity.
    *   `fire="0.4"`: Takes 40% damage from fire.
    *   `holy="0"`: Takes no damage from holy sources.

### Sprite Component

Determines the visual appearance of the entity.

```xml
<SpriteComponent
    image_file="data/entities/animals/boss_spirit/boss_spirit_sprite.xml"
    emissive="1"
    additive="1"
>
</SpriteComponent>
```

*   **`image_file="data/entities/animals/boss_spirit/boss_spirit_sprite.xml"`**: Uses a specific sprite definition file.
*   **`emissive="1"`, `additive="1"`**: Indicates emissive and additive rendering for visual effects.

### PathFinding Component

Defines how the entity navigates the game world.

```xml
<PathFindingComponent
    can_jump="1"
    can_walk="1"
    can_fly="1"
>
</PathFindingComponent>
```

*   **`can_jump="1"`, `can_walk="1"`, `can_fly="1"`**: The Island Spirit can jump, walk, and fly.

### Character Platforming Component

Controls movement mechanics like running and jumping.

```xml
<CharacterPlatformingComponent
    jump_velocity_y="-12"
    run_velocity="18"
>
</CharacterPlatformingComponent>
```

*   **`run_velocity="18"`**: The entity moves at a run velocity of 18 units.

### Hitbox and Collision Components

Define the physical boundaries for interaction and collision.

```xml
<HitboxComponent
    aabb_min_x="-8.5"
    aabb_max_x="8.5"
    aabb_min_y="-10"
    aabb_max_y="5"
>
</HitboxComponent>

<CharacterDataComponent
    collision_aabb_min_x="-5.6"
    collision_aabb_max_x="5.6"
    collision_aabb_min_y="-10"
    collision_aabb_max_y="3"
    mass="2.7"
>
</CharacterDataComponent>
```

*   These components define the bounding boxes for hit detection and physical collisions.

## Audio Components

Handles sound effects and ambient audio.

```xml
<AudioComponent
    file="data/audio/Desktop/animals.bank"
    event_root="animals/ghost" >
</AudioComponent>

<AudioLoopComponent
    file="data/audio/Desktop/animals.bank"
    event_name="animals/ghost/movement_loop"
    set_speed_parameter="1"
    auto_play="1">
</AudioLoopComponent>
```

*   **`event_root="animals/ghost"`**: The base sound event for this entity.
*   **`event_name="animals/ghost/movement_loop"`**: A looping sound played during movement.

## Particle Emitters

Responsible for visual effects like sparks and cosmetic particles.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark_blue"
    gravity.y="-19"
    x_vel_min="-5"
    x_vel_max="5"
    y_vel_min="0"
    y_vel_max="50"
    count_min="1"
    count_max="4"
    lifetime_min="2"
    lifetime_max="20"
    is_emitting="1"
>
</ParticleEmitterComponent>

<ParticleEmitterComponent
    emitted_material_name="spark_white"
    count_min="1"
    count_max="1"
    lifetime_min="5"
    lifetime_max="20"
    create_real_particles="1"
    is_emitting="1"
>
</ParticleEmitterComponent>
```

*   Two emitters are present: one for blue sparks with gravity and velocity, and another for white sparks with a focus on creating real particles.

## Lua Scripting

Custom behaviors and logic are handled by Lua scripts.

```xml
<LuaComponent
    script_source_file="data/entities/animals/boss_spirit/islandspirit.lua"
    script_damage_received="data/entities/animals/boss_spirit/islandspirit.lua"
    script_death="data/entities/animals/boss_spirit/islandspirit.lua"
    execute_every_n_frame="1"
>
</LuaComponent>

<LuaComponent
    script_source_file="data/entities/animals/boss_spirit/init.lua"
    execute_on_added="1"
    remove_after_executed="1"
>
</LuaComponent>
```

*   **`islandspirit.lua`**: Contains general scripts for damage received and death events.
*   **`init.lua`**: Executes once upon entity addition for initialization.

## Protection Effects

The Island Spirit has inherent protections against certain status effects.

```xml
<Entity>
    <InheritTransformComponent />
    <GameEffectComponent effect="STUN_PROTECTION_FREEZE" frames="-1" />
</Entity>
<Entity>
    <InheritTransformComponent />
    <GameEffectComponent effect="STUN_PROTECTION_ELECTRICITY" frames="-1" />
</Entity>
<Entity>
    <InheritTransformComponent />
    <GameEffectComponent effect="PROTECTION_PROJECTILE" frames="-1" />
</Entity>
```

*   These entities grant permanent (`frames="-1"`) protection against freeze, electricity, and projectiles.

## Health Bar UI

Components for displaying the boss's health bar.

```xml
<SpriteComponent _tags="health_bar_back,ui" ... image_file="data/ui_gfx/health_slider_back.png" ... >
</SpriteComponent>

<SpriteComponent _tags="health_bar,ui" ... image_file="data/ui_gfx/health_slider_front.png" ... >
</SpriteComponent>

<BossHealthBarComponent>
</BossHealthBarComponent>
```

*   These components define the visual elements and functionality for the boss health bar.

## Cosmetic Particle Emitter

A final particle emitter for ambient visual effects.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark"
    lifetime_min="0.5"
    lifetime_max="1.2"
    count_min="2"
    count_max="4"
    render_on_grid="1"
    area_circle_radius.min="32"
    area_circle_radius.max="72"
    airflow_force="1.5"
    is_emitting="1"
    velocity_always_away_from_center="240"
>
</ParticleEmitterComponent>
```

*   This emitter creates cosmetic sparks with a radial outward velocity.