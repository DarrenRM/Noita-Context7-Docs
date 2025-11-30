---
title: Boss Meat Entity
category: entities
---

# Boss Meat Entity

This document details the `boss_meat.xml` entity, a formidable boss creature in Noita. It outlines its core attributes, AI behaviors, physics, damage properties, and visual components.

## Core Attributes

The `Entity` tag defines the fundamental properties of the Boss Meat.

-   **`tags`**: A comma-separated list of tags that categorize the entity. Key tags include:
    -   `enemy`: Identifies it as a hostile creature.
    -   `mortal`: Indicates it can be killed.
    -   `hittable`: Can be targeted and damaged.
    -   `boss`: Designates it as a boss-level enemy.
    -   `miniboss`: Further specifies its role as a significant, but not ultimate, boss.
    -   `music_energy_100`: Likely relates to its contribution to in-game music or energy levels.
-   **`name`**: `$animal_boss_meat` - The internal name for this entity.

## Visual Components

These components define the appearance and visual effects of the Boss Meat.

### Sprite Components

-   **Main Body Sprite**:
    ```xml
    <SpriteComponent 
        _tags="character"
        image_file="data/entities/animals/boss_meat/body.xml" 
        offset_y="24"
        offset_x="24" >
    </SpriteComponent>
    ```
    This defines the primary visual representation of the boss, referencing an external XML for its detailed sprite data.

-   **Health Bar Sprites**: Two `SpriteComponent`s are used to render the boss's health bar, one for the background and one for the foreground.
    -   `image_file`: Specifies the texture for the health bar segments (`health_slider_back_meat.png` and `health_slider_front.png`).
    -   `z_index`: `-9000` and `-9001` ensure the health bar is rendered above other game elements.

### Light Component

-   **`LightComponent`**:
    ```xml
    <LightComponent 
        _enabled="1" 
        radius="256"
        r="100"
        g="255"
        b="130"
        offset_y="0"
        fade_out_time="1.5" >
    </LightComponent>
    ```
    This component adds a greenish light effect around the boss with a radius of 256 pixels, fading out over 1.5 seconds.

## AI and Behavior

These components control the Boss Meat's actions and interactions.

### AI Components

-   **`LimbBossComponent`**:
    ```xml
    <LimbBossComponent
        state="1"
        >
    </LimbBossComponent>
    ```
    This component likely manages the boss's limb-based behaviors or states.

-   **`LuaComponent` (AI Scripts)**: Multiple `LuaComponent`s are used to implement complex AI behaviors.
    -   **Eye Behavior**:
        ```lua
        <LuaComponent
            script_source_file="data/entities/animals/boss_meat/eye.lua"
            execute_every_n_frame="80"
            >
        </LuaComponent>
        ```
        Executes the `eye.lua` script every 80 frames, likely for targeting or visual eye animations.
    -   **Shot Behavior**:
        ```lua
        <LuaComponent
            _tags="vacuum_NOT"
            script_source_file="data/entities/animals/boss_meat/shot.lua"
            execute_every_n_frame="20"
            >
        </LuaComponent>
        ```
        Handles projectile attacks, running every 20 frames.
    -   **Vacuum Behavior**:
        ```lua
        <LuaComponent
            _tags="vacuum"
            _enabled="0"
            script_source_file="data/entities/animals/boss_meat/vacuum.lua"
            execute_every_n_frame="1"
            >
        </LuaComponent>
        ```
        This script is initially disabled (`_enabled="0"`) and controls a vacuum-like ability, running every frame when active.

-   **`BlackHoleComponent`**:
    ```xml
    <BlackHoleComponent
        _tags="vacuum"
        _enabled="0"
        particle_attractor_force="-3"
        damage_probability="0"
        radius="128">
    </BlackHoleComponent>
    ```
    When enabled (along with the `vacuum` tag), this component creates a black hole effect that attracts particles within a 128-pixel radius.

-   **`AreaDamageComponent`**:
    ```xml
    <AreaDamageComponent
        _tags="vacuum"
        _enabled="0"
        aabb_min.x="-20" 
        aabb_min.y="-20" 
        aabb_max.x="20" 
        aabb_max.y="20" 
        damage_per_frame="0.15"
        update_every_n_frame="1"
        entities_with_tag="player_unit"
        death_cause="$animal_boss_meat"
        damage_type="DAMAGE_MELEE"
        circle_radius="20"
        >
    </AreaDamageComponent>
    ```
    This component, also tied to the `vacuum` tag and initially disabled, deals melee damage to players within its radius when the vacuum ability is active.

-   **`PathFindingComponent`**:
    ```xml
    <PathFindingComponent 
        can_dive="1" 
        can_fly="1" 
        can_jump="0" 
        can_walk="0" 
        cost_of_flying="500" 
        initial_jump_max_distance_x="100" 
        initial_jump_max_distance_y="60" 
        jump_speed="200" 
        max_jump_distance_from_camera="400" >
    </PathFindingComponent>
    ```
    Configures the entity's pathfinding capabilities, allowing it to fly but not walk, dive, or jump. It defines parameters for flight and jump mechanics.

-   **`PathFindingGridMarkerComponent`**:
    ```xml
    <PathFindingGridMarkerComponent 
        _enabled="1" 
        marker_offset_x="0" 
        marker_offset_y="-6" 
        marker_work_flag="16" >
    </PathFindingGridMarkerComponent>
    ```
    Marks the entity's position on the pathfinding grid.

## Physics

These components govern the physical interactions of the Boss Meat.

### Physics Components

-   **`PhysicsAIComponent`**:
    ```xml
    <PhysicsAIComponent
        target_vec_max_len="15.0"
        force_coeff="17.0"
        force_max="100"
        torque_coeff="50"
        torque_max="50.0" >
    </PhysicsAIComponent>
    ```
    Controls the AI's influence on the entity's physics, defining forces and torque applied for movement and stabilization.

-   **`PhysicsBodyComponent`**:
    ```xml
    <PhysicsBodyComponent 
        allow_sleep="1" 
        angular_damping="0.02" 
        fixed_rotation="0" 
        linear_damping="0"  >
    </PhysicsBodyComponent>
    ```
    Defines the basic physical properties of the entity's body, including damping and rotation.

-   **`PhysicsShapeComponent`**:
    ```xml
    <PhysicsShapeComponent
        is_circle="1"
        radius_x="14"
        radius_y="14"
        friction="0.0"
        restitution="0.3" >
    </PhysicsShapeComponent>
    ```
    Defines the collision shape as a circle with a radius of 14, and sets friction and restitution values.

## Damage and Health

These components manage the Boss Meat's health, damage resistances, and how it reacts to damage.

### Damage Components

-   **`DamageModelComponent`**:
    ```xml
    <DamageModelComponent 
        hp="40" 
        fire_damage_amount="0.2" 
        blood_material="blood_fading"
        materials_damage="1" 
        materials_how_much_damage="0" 
        ragdoll_material="meat"
        ragdoll_offset_y="-6"
        ragdollify_child_entity_sprites="1" 
        blood_sprite_directional="data/particles/bloodsplatters/bloodsplatter_directional_$[1-3].xml"
        blood_sprite_large="data/particles/bloodsplatters/bloodsplatter_$[1-3].xml"
        >
        <damage_multipliers
            melee="0.6"
            projectile="0.4"
            explosion="0.5"
            fire="1.2" 
            drill="0.9"
            slice="1.1"
            >
        </damage_multipliers>
    </DamageModelComponent>
    ```
    -   **`hp`**: 40 - The entity's health points.
    -   **`blood_material`**: `blood_fading` - The material used for blood effects.
    -   **`ragdoll_material`**: `meat` - The material used for its ragdoll.
    -   **`damage_multipliers`**: Defines resistances and vulnerabilities to different damage types. It takes 60% melee damage, 40% projectile damage, 50% explosion damage, 120% fire damage, 90% drill damage, and 110% slice damage.

-   **`GenomeDataComponent`**:
    ```xml
    <GenomeDataComponent 
        food_chain_rank="5" 
        herd_id="slimes" 
        is_predator="1" >
    </GenomeDataComponent>
    ```
    -   **`food_chain_rank`**: 5 - Its position in the food chain.
    -   **`is_predator`**: 1 - Indicates it is a predator.

-   **`HitboxComponent`**:
    ```xml
    <HitboxComponent 
        _tags="hitbox_default"
        aabb_min_x="-20" 
        aabb_max_x="20" 
        aabb_min_y="-20" 
        aabb_max_y="20"
        damage_multiplier="0" >
    </HitboxComponent>
    ```
    Defines the default hitbox for the entity, with no damage multiplier.

## Other Components

### Miscellaneous Components

-   **`AudioComponent`**:
    ```xml
    <AudioComponent 
        file="data/audio/Desktop/animals.bank"
        event_root="animals" >
    </AudioComponent>
    ```
    Manages the entity's sound effects, referencing the `animals.bank` audio file.

-   **`SpriteAnimatorComponent`**:
    ```xml
    <SpriteAnimatorComponent 
        rotate_to_surface_normal="0" 
        target_sprite_comp_name="character" >
    </SpriteAnimatorComponent>
    ```
    Handles sprite animations, targeting the main character sprite.

-   **`CellEaterComponent`**:
    ```xml
    <CellEaterComponent
        radius="36" 
        eat_probability="100">
    </CellEaterComponent>
    ```
    Allows the entity to consume cells within a 36-pixel radius with 100% probability.

-   **`BossHealthBarComponent`**:
    ```xml
    <BossHealthBarComponent
        in_world="1"
    ></BossHealthBarComponent>
    ```
    Enables the display of a boss-specific health bar in the game world.

-   **`LuaComponent` (Death Script)**:
    ```lua
    <LuaComponent
        script_death="data/entities/animals/boss_meat/death.lua"
        >
    </LuaComponent>
    ```
    Executes `death.lua` when the entity dies, handling death animations or effects.

-   **`AudioComponent` (Boss Limbs)**:
    ```xml
    <AudioComponent
      file="data/audio/Desktop/animals.bank"
      event_root="animals/boss_limbs"
      set_latest_event_position="1" >
    </AudioComponent>
    ```
    Specific audio component for boss limb sounds.

## Attached Entities

The Boss Meat entity is composed of several attached entities, primarily limbs and tentacles, which are defined using `<Entity>` and `<Base>` tags.

### Limbs

-   Twelve instances of `data/entities/animals/boss_meat/limb.xml` are attached, forming the boss's primary limbs.

### Tentacles (Hair)

-   Various "hair" entities (`hair1.xml`, `hair2.xml`, `hair3.xml`) are attached to form tentacles.
-   Each tentacle entity uses `<InheritTransformComponent>` to define its specific `position.x` and `position.y` relative to the main boss body, creating a varied distribution.

### Particle Emitter

-   **`ParticleEmitterComponent`**:
    ```xml
    <ParticleEmitterComponent
        _tags="vacuum"
        _enabled="0"
        emitted_material_name="spark_red"
        lifetime_min="0.5"
        lifetime_max="1.2"
        count_min="20"
        count_max="30"
        area_circle_radius.min="32"
        area_circle_radius.max="72"
        airflow_force="1.5"
        velocity_always_away_from_center="240"
        >
    </ParticleEmitterComponent>
    ```
    When the `vacuum` behavior is active, this component emits red sparks with specific lifetime, count, and velocity properties, creating a visual effect for the vacuum ability.