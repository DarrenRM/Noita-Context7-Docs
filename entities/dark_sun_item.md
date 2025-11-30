---
title: Dark Sun Item
category: entities
---

# Dark Sun Item

This document describes the "Dark Sun" item in Noita, focusing on its attributes and behaviors relevant to AI-assisted modding.

## Core Attributes

The Dark Sun is an entity with several key components that define its functionality:

*   **`tags`**: `hittable`, `teleportable_NOT`, `seed_f` - Indicates it can be hit, cannot be teleported, and is associated with the "seed_f" item type.
*   **`Base file="data/entities/base_item_projectile.xml"`**: Inherits properties from a base item projectile, suggesting it can be thrown or dropped.
*   **`SpriteComponent`**:
    *   `image_file="data/props_gfx/sun_big_dark.png"`: Defines the visual appearance.
    *   `emissive="1"`: The sprite emits light.
    *   `offset_x="160"`, `offset_y="160"`: Adjusts the sprite's position.
*   **`UIInfoComponent`**:
    *   `name="$item_seed_f"`: The in-game name displayed to the player.

## Functional Components

### Material Conversion

The Dark Sun has multiple `MagicConvertMaterialComponent` instances, allowing it to transform surrounding materials:

*   **Primary Conversion**:
    *   `to_material="material_darkness"`: Converts nearby materials into "material\_darkness".
    *   `convert_entities="1"`: Also converts entities.
    *   `radius="100"`: The radius of this conversion effect.
    *   `loop="1"`: The conversion effect repeats.
*   **Alchemy Conversion**:
    *   `from_material_tag="[alchemy]"`: Specifically targets materials with the "alchemy" tag.
    *   `radius="230"`: A larger radius for alchemy conversion.
*   **Extinguishing Effect**:
    *   `extinguish_fire="1"`: Extinguishes fire in its vicinity.
    *   `radius="270"`: The radius for extinguishing fire.

### Environmental Effects

*   **`CellEaterComponent`**:
    *   `radius="130"`: Defines the radius within which it consumes cells (materials).
    *   `eat_probability="80"`: 80% chance to eat a cell.
    *   `ignored_material="gem_box2d_yellow_sun"`: Does not consume this specific material.
*   **`AreaDamageComponent`**: Multiple instances create damage zones with different properties:
    *   **Inner Zone (Radius ~122)**:
        *   `damage_per_frame="2.14"`
        *   `damage_type="DAMAGE_CURSE"`
    *   **Mid Zone (Radius ~190)**:
        *   `damage_per_frame="1.05"`
        *   `damage_type="DAMAGE_ICE"`
    *   **Outer Zone (Radius ~280)**:
        *   `damage_per_frame="0.61"`
        *   `damage_type="DAMAGE_ELECTRICITY"`
    *   All damage components target entities with the tag `mortal`.
*   **`BlackHoleComponent`**:
    *   `radius="280"`: Creates an attraction effect within this radius.
    *   `particle_attractor_force="8"`: The strength of the attraction.
    *   `damage_probability="0.25"`: Chance to deal damage to attracted entities.

### Visual and Audio Effects

*   **`ParticleEmitterComponent`**: Two instances emit cosmetic particles:
    *   One emits `spark_purple_bright`.
    *   The other emits `spark_blue_dark`.
    *   Both have a radius of 64-96, velocity away from the center, and a lifetime of 0.1-2.4 seconds.
*   **`AudioLoopComponent`**:
    *   `event_name="misc/sun/size_3_loop"`: Plays a looping sound effect.

### Scripted Behavior

*   **`LuaComponent`**:
    *   `script_source_file="data/scripts/buildings/sun/sun_controls.lua"`: Executes Lua script for general sun controls.
    *   `script_source_file="data/scripts/buildings/sun/sun_dark_effect.lua"`: Executes Lua script for specific dark effect behaviors.

### Other Components

*   **`StreamingKeepAliveComponent`**: Ensures the entity remains loaded.
*   **`PhysicsBodyComponent`**: Defines its physical properties.
*   **`PhysicsKeepInWorldComponent`**: Keeps the physics body within the world bounds.
*   **`VelocityComponent`**: Manages its velocity.
*   **`LooseGroundComponent`**: Can cause nearby ground to become loose.
*   **`MusicEnergyAffectorComponent`**: Affects music energy.