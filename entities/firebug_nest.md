---
title: Firebug Nest
category: entities
---

# Firebug Nest

This document details the `firebugnest.xml` entity, representing a Firebug Nest in Noita. It outlines its core attributes and components relevant to AI-assisted modding.

## Core Entity Attributes

*   **name**: `unknown` (This is a placeholder and should ideally be more descriptive for modding purposes.)
*   **tags**: `mortal, nest, predator, hittable, glue_NOT`
    *   `mortal`: The nest can be destroyed.
    *   `nest`: Identifies this entity as a type of nest.
    *   `predator`: Indicates it's a predator in the game's ecosystem.
    *   `hittable`: The nest can be targeted and damaged.
    *   `glue_NOT`: Suggests it's not affected by glue in a specific way.

## Key Components

### DamageModelComponent

Manages the health, damage taken, and death behavior of the nest.

*   **hp**: `5` - Current health points.
*   **max_hp**: `5` - Maximum health points.
*   **fire_damage_amount**: `0.2` - Damage taken from fire.
*   **materials_damage**: `1` - Indicates that materials can damage the nest.
*   **materials_that_damage**: `acid, poison, blood_cold, blood_cold_vapour` - List of materials that inflict damage.
*   **materials_how_much_damage**: `0.004,0.001,0.0008,0.0007` - Corresponding damage values for each material.
*   **drop_items_on_death**: `1` - The nest drops items when destroyed.
*   **blood_material**: `lava` - The material that spills from the nest upon taking damage or dying.

### GenomeDataComponent

Defines the ecological role and behavior of the nest.

*   **food_chain_rank**: `20` - Its position in the food chain.
*   **herd_id**: `nest` - Identifies it as part of a "nest" group.
*   **is_predator**: `1` - Confirms it's a predator.

### ItemChestComponent

Determines the loot dropped by the nest.

*   **item_count_min**: `3` - Minimum number of items dropped.
*   **item_count_max**: `4` - Maximum number of items dropped.
*   **level**: `3` - The quality or tier of items dropped.

### HitboxComponent

Defines the physical collision area of the nest.

*   **aabb_min_x**, **aabb_max_x**, **aabb_min_y**, **aabb_max_y**: Define the bounding box for collision detection.

### LuaComponent

Links the entity to its associated script for custom behavior.

*   **script_source_file**: `data/scripts/buildings/firebugnest.lua` - The path to the Lua script controlling its logic.
*   **execute_every_n_frame**: `121` - How often the script's logic is executed.
*   **execute_times**: `-1` - The script will execute indefinitely.

### SpriteComponent (Primary)

Defines the visual appearance of the nest.

*   **image_file**: `data/buildings_gfx/nest_yellow.xml` - The primary graphical asset for the nest.

### ParticleEmitterComponent

Manages the emission of particles from the nest.

*   **emitted_material_name**: `spark` - The type of particle emitted.
*   **count_min**, **count_max**: `1`, `2` - Number of particles emitted per burst.
*   **x_vel_min**, **y_vel_min**, **x_vel_max**, **y_vel_max**: Define the velocity range of emitted particles.
*   **lifetime_min**, **lifetime_max**: `0.1`, `0.3` - Duration of each particle.
*   **emission_interval_min_frames**, **emission_interval_max_frames**: `20`, `40` - Frequency of particle emission.
*   **is_emitting**: `1` - The particle emitter is active.

### SpriteComponent (Emissive)

Adds an emissive visual effect.

*   **image_file**: `data/buildings_gfx/nest_emissive_alt.xml` - The graphical asset for the emissive effect.
*   **emissive**: `1` - Enables emissive properties.
*   **additive**: `1` - Uses additive blending for the emissive effect.

### LightComponent

Adds a light source originating from the nest.

*   **radius**: `120` - The range of the light.
*   **r**, **g**, **b**: `205`, `145`, `20` - The RGB color values of the light (a yellowish-orange).