---
title: HPCrystal Entity
category: entities
---

# HPCrystal Entity

This document details the `hpcrystal.xml` entity, a building-type entity in Noita. It's designed to be a stationary object with specific damage properties and visual effects.

## Key Components and Attributes

### Entity Definition

*   **name**: `$animal_hpcrystal` - Internal identifier for the entity.
*   **tags**: `hittable`, `mortal` - Indicates the entity can be hit and can be destroyed.

### DamageModelComponent

This component governs how the HPCrystal takes damage and its resistances.

*   **hp**: `20` - The total health points of the HPCrystal.
*   **fire_damage_amount**: `0.2` - The amount of damage taken from fire per tick.
*   **materials_damage**: `1` - Enables damage from colliding materials.
*   **ragdoll_material**: `ice_b2` - The material used for its ragdoll when destroyed.
*   **damage_multipliers**: Defines how much damage the entity takes from different damage types.
    *   `fire`: `0.2` (Resistant to fire)
    *   `ice`: `1.0` (Normal damage from ice)
    *   `drill`: `1.2` (Takes extra damage from drills)
    *   `slice`: `0.0` (Immune to slicing damage)
    *   `melee`: `0.8` (Takes slightly less melee damage)
    *   `projectile`: `0.3` (Takes significantly less projectile damage)
    *   `explosion`: `0.5` (Takes half damage from explosions)
    *   `electricity`: `0.0` (Immune to electricity)

### GenomeDataComponent

This component is typically used for AI-driven creatures but is present here, suggesting potential for future AI integration or a placeholder.

*   **food_chain_rank**: `20` - A numerical value representing its position in a food chain.
*   **herd_id**: `ghost` - An identifier for grouping or AI behavior.
*   **is_predator**: `1` - Indicates it might be considered a predator in its AI context.

### HitboxComponent

Defines the physical boundaries of the entity for interactions.

*   **aabb_max_x**: `6`, **aabb_max_y**: `0` - Maximum X and Y coordinates relative to the entity's center.
*   **aabb_min_x**: `-6`, **aabb_min_y**: `-20` - Minimum X and Y coordinates relative to the entity's center.
*   **is_player**: `1` - This is unusual and might indicate it can be targeted by player-like mechanics or has player-like collision properties.

### SpriteComponent

Controls the visual representation of the HPCrystal.

*   **image_file**: `data/buildings_gfx/hpcrystal.xml` - Points to the graphical assets for the entity.
*   **rect_animation**: `stand` - Specifies the default animation state.

### LuaComponent

Attaches a Lua script to the entity for custom behavior.

*   **script_source_file**: `data/scripts/buildings/hpcrystal.lua` - The path to the Lua script that controls the entity's logic.
*   **execute_every_n_frame**: `240` - The script will execute its logic every 240 frames.

### ParticleEmitterComponent

Manages the emission of particles from the entity.

*   **emitted_material_name**: `spark_green` - The type of particle emitted.
*   **lifetime_min/max**: `1`/`3` - Duration of emitted particles.
*   **x_vel_min/max**: `-5`/`5` - Horizontal velocity range of particles.
*   **y_vel_min/max**: `-20`/`5` - Vertical velocity range of particles.
*   **count_min/max**: `15`/`15` - Number of particles emitted per burst.
*   **emission_interval_min/max_frames**: `12`/`12` - How often particles are emitted.
*   **area_circle_radius.max**: `11` - The radius of the area from which particles are emitted.
*   **is_emitting**: `1` - Enables particle emission.

### LightComponent

Adds a light source to the entity.

*   **radius**: `80` - The range of the light.
*   **r**, **g**, **b**: `45`, `250`, `165` - Defines the color of the light (a greenish-cyan).