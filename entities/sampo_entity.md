---
title: Sampo Entity
category: entities
---

# Sampo Entity

This document details the configuration of the Sampo entity in Noita, focusing on its attributes and components relevant to AI-assisted modding.

## Core Entity Definition

The Sampo is a unique entity, tagged for teleportation exclusion and identified as a McGuffin, often associated with boss encounters.

```xml
<Entity tags="teleportable_NOT,sampo_or_boss,this_is_sampo">
```

## Key Components

The Sampo entity is defined by a collection of components that dictate its behavior, appearance, and interactions.

### UI Information

Provides the in-game name and description for the Sampo.

```xml
<UIInfoComponent
    name="$item_mcguffin"
    >
</UIInfoComponent>
```

### Physics and Movement

Basic physics and velocity components are included, suggesting it can be affected by game physics.

```xml
<VelocityComponent />
<SimplePhysicsComponent/>
```

### Item Properties

Defines the Sampo as a pickable item with specific UI elements and inventory behavior.

```xml
<ItemComponent
    _tags="enabled_in_world"
    item_name="$item_mcguffin"
    is_pickable="1"
    ui_sprite="data/ui_gfx/items/sampo.png"
    ui_description="$itemdesc_mcguffin"
    preferred_inventory="FULL"
    uses_remaining="-1"
    play_spinning_animation="0"
    play_hover_animation="1"
    >
</ItemComponent>
```

### Lua Scripting

Multiple Lua components manage the Sampo's behavior, including pickup actions, initialization, and the start of ending sequences.

*   **Pickup Script:** Executes when the item is picked up.
    ```xml
    <LuaComponent
        script_item_picked_up="data/entities/animals/boss_centipede/sampo_pickup.lua"
        remove_after_executed="1"
    >
    </LuaComponent>
    ```
*   **Initialization Script:** Runs when the entity is added to the world.
    ```xml
    <LuaComponent
        _enabled="1"
        execute_on_added="1"
        remove_after_executed="1"
        script_source_file="data/entities/animals/boss_centipede/sampo_init.lua"
    >
    </LuaComponent>
    ```
*   **Ending Sequence Script:** Triggers the start of a specific ending sequence.
    ```xml
    <LuaComponent
        _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"
        _enabled="1"
        script_source_file="data/entities/animals/boss_centipede/ending/sampo_start_ending_sequence.lua"
        execute_every_n_frame="-1"
        >
    </LuaComponent>
    ```

### Transform Inheritance

Ensures the Sampo's transform is inherited from its parent, relevant for its placement and movement within the game world.

```xml
<InheritTransformComponent
    _tags="enabled_in_world,enabled_in_hand,enabled_in_inventory"
    use_root_parent="1" >
</InheritTransformComponent>
```

### Ending McGuffin Component

A specific component likely related to its role as a key item in certain game endings. It's disabled by default when in inventory.

```xml
<EndingMcGuffinComponent
    _enabled="0"
    _tags="enabled_in_inventory">
</EndingMcGuffinComponent>
```

### Visual Representation

Defines the sprite used to render the Sampo in the game world and when held.

```xml
<SpriteComponent
    _tags="enabled_in_world,enabled_in_hand"
    image_file="data/entities/animals/boss_centipede/sampo_sprite.xml"
    offset_x="12"
    offset_y="12"
    z_index="0.5"
    >
</SpriteComponent>
```

### Particle Emitters

Several `ParticleEmitterComponent` instances are used to create visual effects:

*   **World/Hand Particles:** Emits blue sparks when the Sampo is in the world or held.
    ```xml
    <ParticleEmitterComponent
        _tags="enabled_in_world,enabled_in_hand"
        emitted_material_name="spark_blue"
        gravity.y="0.0"
        lifetime_min="1"
        lifetime_max="3"
        x_vel_min="-5"
        x_vel_max="5"
        y_vel_min="-20"
        y_vel_max="5"
        count_min="55"
        count_max="55"
        render_on_grid="1"
        fade_based_on_lifetime="1"
        cosmetic_force_create="1"
        collide_with_grid="0"
        airflow_force="0.151"
        airflow_time="1.01"
        airflow_scale="0.03"
        emission_interval_min_frames="12"
        emission_interval_max_frames="12"
        emit_cosmetic_particles="1"
        area_circle_radius.max="12"
        render_back="1"
        is_emitting="1" >
    </ParticleEmitterComponent>
    ```
*   **Inventory Particles (Yellow Sparks):** Emits yellow sparks when the Sampo is in the inventory.
    ```xml
    <ParticleEmitterComponent
        _tags="enabled_in_inventory"
        emitted_material_name="spark_yellow"
        gravity.y="0.0"
        lifetime_min="1.5"
        lifetime_max="8.5"
        count_min="0"
        count_max="1"
        render_on_grid="1"
        fade_based_on_lifetime="1"
        area_circle_radius.max="6"
        cosmetic_force_create="0"
        airflow_force="0.5"
        airflow_time="0.01"
        airflow_scale="0.05"
        attractor_force="2"
        emission_interval_min_frames="4"
        emission_interval_max_frames="30"
        emit_cosmetic_particles="1"
        is_emitting="1" >
    </ParticleEmitterComponent>
    ```
*   **Inventory Particles (Gold):** Emits gold particles when the Sampo is in the inventory.
    ```xml
    <ParticleEmitterComponent
        _tags="enabled_in_inventory"
        emitted_material_name="gold"
        gravity.y="0.0"
        lifetime_min="2.5"
        lifetime_max="13.5"
        count_min="0"
        count_max="1"
        render_on_grid="1"
        fade_based_on_lifetime="1"
        area_circle_radius.max="4"
        cosmetic_force_create="0"
        airflow_force="0.5"
        airflow_time="0.01"
        airflow_scale="0.05"
        attractor_force="2"
        emission_interval_min_frames="4"
        emission_interval_max_frames="30"
        emit_cosmetic_particles="1"
        >
    </ParticleEmitterComponent>
    ```

### Music Energy Affector

Influences the game's music energy based on proximity.

```xml
<MusicEnergyAffectorComponent
    energy_target="1.0"
    fade_range="600.0"
    fog_of_war_threshold="255"
    energy_lerp_up_speed_multiplier="5.0"
    >
</MusicEnergyAffectorComponent>
```

### Material Area Checker and Charm Script

This section, marked with comments, appears to be a temporary or experimental feature related to checking for specific materials and potentially applying a "wand charm" effect via a Lua script.

```xml
<MaterialAreaCheckerComponent
    _tags="enabled_in_world"
    update_every_x_frame="20"
    look_for_failure="0"
    area_aabb.min_x="-2"
    area_aabb.min_y="-4"
    area_aabb.max_x="2"
    area_aabb.max_y="0"
    material="magic_liquid_charm"
    material2="magic_liquid_charm"
    kill_after_message="0"
    />

<LuaComponent
    _tags="enabled_in_world"
    script_material_area_checker_success="data/scripts/animals/wand_charm.lua" >
</LuaComponent>
```