---
title: Sunbaby Item
category: entities
---

# Sunbaby Item

This document details the `sunbaby.xml` entity, which represents a unique item in Noita. It's designed to interact with the environment and entities through various damage and material conversion effects, often associated with solar or fiery properties.

## Core Components

The Sunbaby item is built upon several fundamental components that define its behavior and appearance.

### Base Item

*   **`Base file="data/entities/base_item_projectile.xml"`**: Inherits core properties of a projectile item, suggesting it can be thrown or launched.

### Physics and Movement

*   **`PhysicsBodyComponent`**: Defines the physical presence of the item.
    *   `allow_sleep="0"`: The physics body will not go to sleep, ensuring continuous interaction.
    *   `fixed_rotation="0"`: Allows the item to rotate freely.
    *   `gravity_scale_if_has_no_image_shapes="0"`: Prevents gravity from affecting it if it lacks visual shapes.
*   **`PhysicsKeepInWorldComponent`**: Ensures the item remains within the game world boundaries.
*   **`VelocityComponent`**: Manages the item's velocity and its interaction with physics.

### Visuals

*   **`SpriteComponent` (Fog of War)**:
    *   `image_file="data/particles/fog_of_war_hole_huge.png"`: Creates a visual effect resembling a large hole in the fog of war.
    *   `fog_of_war_hole="1"`: Actively modifies the fog of war.
*   **`SpriteComponent` (Sun)**:
    *   `image_file="data/props_gfx/sun_small.png"`: Displays a small sun graphic.
    *   `emissive="1"`: The sprite emits light.
    *   `additive="1"`: The sprite uses additive blending for a brighter effect.

### Information

*   **`UIInfoComponent`**:
    *   `name="$item_seed_d"`: Assigns a localized name to the item, likely "Seed D" or similar.

## Interaction and Effects

The Sunbaby's primary function is its interaction with the environment and entities through various damage and material manipulation effects. These effects are often conditional based on tags.

### Material Conversion (`MagicConvertMaterialComponent`)

This component allows the Sunbaby to convert surrounding materials. Multiple instances with different tags and configurations exist.

*   **Water Conversion**:
    *   `_tags="water"`: Activated when in contact with water.
    *   `to_material="lava"`: Converts materials to lava.
    *   `radius="270"`: The area of effect for conversion.
    *   `loop="1"`: The conversion effect repeats.
*   **Fire Ignition (Conditional)**:
    *   `_tags="fire_disable"`: This configuration is *disabled* when the "fire" tag is present.
    *   `ignite_materials="1"`: Ignites nearby materials.
    *   `radius="140"`: The area of effect.
    *   `fan_the_flames="1"`: Enhances the spread of fire.
*   **Fire Ignition (Active)**:
    *   `_tags="fire"`: Activated when the "fire" tag is present.
    *   `_enabled="0"`: This configuration is *disabled* by default.
    *   `ignite_materials="1"`: Ignites nearby materials.
    *   `radius="270"`: The area of effect.

### Cell Eating (`CellEaterComponent`)

This component allows the Sunbaby to consume specific materials from the environment.

*   **Earth Consumption (Conditional)**:
    *   `_tags="earth"`: Activated when in contact with earth.
    *   `_enabled="0"`: This configuration is *disabled* by default.
    *   `radius="190"`: The radius of the eating effect.
    *   `eat_probability="80"`: High chance to eat materials.
    *   `ignored_material_tag="[sunbaby_ignore_list]"`: Specifies materials that should not be eaten.
*   **Earth Consumption (Secondary)**:
    *   `_tags="earth_disable"`: This configuration is *disabled* when the "earth" tag is present.
    *   `radius="120"`: The radius of the eating effect.
    *   `eat_probability="40"`: Moderate chance to eat materials.

### Area Damage (`AreaDamageComponent`)

The Sunbaby inflicts damage to entities within its radius. Different configurations apply based on tags.

*   **Base Damage (Curse)**:
    *   `damage_per_frame="1.14"`: Moderate damage.
    *   `damage_type="DAMAGE_CURSE"`: Inflicts curse damage.
    *   `circle_radius="72"`: The area of effect.
*   **Fire Damage (Conditional)**:
    *   `_tags="fire_disable"`: This configuration is *disabled* when the "fire" tag is present.
    *   `damage_per_frame="0.65"`: Lower damage.
    *   `damage_type="DAMAGE_EXPLOSION"`: Inflicts explosion damage.
    *   `circle_radius="95"`: The area of effect.
*   **Fire Damage (Active)**:
    *   `_tags="fire"`: Activated when the "fire" tag is present.
    *   `_enabled="0"`: This configuration is *disabled* by default.
    *   `damage_per_frame="0.65"`: Lower damage.
    *   `damage_type="DAMAGE_EXPLOSION"`: Inflicts explosion damage.
    *   `circle_radius="130"`: The area of effect.
*   **Fire Damage (Secondary)**:
    *   `_tags="fire_disable"`: This configuration is *disabled* when the "fire" tag is present.
    *   `damage_per_frame="0.21"`: Low damage.
    *   `damage_type="DAMAGE_FIRE"`: Inflicts fire damage.
    *   `circle_radius="120"`: The area of effect.
*   **Fire Damage (Tertiary)**:
    *   `_tags="fire"`: Activated when the "fire" tag is present.
    *   `_enabled="0"`: This configuration is *disabled* by default.
    *   `damage_per_frame="0.21"`: Low damage.
    *   `damage_type="DAMAGE_FIRE"`: Inflicts fire damage.
    *   `circle_radius="180"`: The area of effect.

## Particle Emitters

The Sunbaby emits various particles to visually represent its effects. Different particle types are emitted based on tags.

*   **Yellow Sparks (`sunbaby_stage_2`)**:
    *   `emitted_material_name="spark_yellow"`: Emits yellow sparks.
    *   `velocity_always_away_from_center="250"`: Particles are pushed outwards.
    *   `count_min="40"`, `count_max="60"`: Emits a moderate number of particles.
*   **White Sparks (`sunbaby_stage_1`)**:
    *   `emitted_material_name="spark"`: Emits white sparks.
    *   `velocity_always_away_from_center="250"`: Particles are pushed outwards.
*   **Blue Dark Sparks (`water`)**:
    *   `_tags="water"`: Emitted when interacting with water.
    *   `emitted_material_name="spark_blue_dark"`: Emits dark blue sparks.
    *   `velocity_always_away_from_center="300"`: Particles are pushed outwards with more force.
*   **Red Sparks (`fire`)**:
    *   `_tags="fire"`: Emitted when interacting with fire.
    *   `emitted_material_name="spark_red"`: Emits red sparks.
    *   `velocity_always_away_from_center="400"`: Particles are pushed outwards with significant force.
*   **Blue Sparks (`air`)**:
    *   `_tags="air"`: Emitted when interacting with air.
    *   `emitted_material_name="spark_blue"`: Emits blue sparks.
    *   `velocity_always_away_from_center="400"`: Particles are pushed outwards with significant force.
*   **Green Sparks (`earth`)**:
    *   `_tags="earth"`: Emitted when interacting with earth.
    *   `emitted_material_name="spark_green"`: Emits green sparks.
    *   `velocity_always_away_from_center="200"`: Particles are pushed outwards.

## Audio and Scripting

*   **`AudioLoopComponent`**:
    *   `event_name="misc/sun/size_2_loop"`: Plays a looping sound effect associated with the sun.
*   **`LuaComponent` (Spot Effect)**:
    *   `script_source_file="data/scripts/buildings/sun/spot_4.lua"`: Executes a script for a specific visual or functional effect.
*   **`VariableStorageComponent`**:
    *   `name="sunbaby_essences_list"`: Stores a list of essences, likely related to its effects.
*   **`LuaComponent` (Air Effect)**:
    *   `_tags="air"`: This script is activated when the "air" tag is present.
    *   `_enabled="0"`: Disabled by default.
    *   `script_source_file="data/scripts/buildings/sun/sunbaby_air_effect.lua"`: Executes a script for air-related effects.
*   **`LuaComponent` (Controls)**:
    *   `script_source_file="data/scripts/buildings/sun/sunbaby_controls.lua"`: Executes a script that likely manages the Sunbaby's overall behavior and interactions.