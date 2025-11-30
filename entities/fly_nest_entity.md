---
title: Fly Nest Entity
category: entities
---

# Fly Nest Entity

This document describes the `flynest.xml` entity, which represents a fly nest in Noita. It details its core attributes, damage mechanics, visual representation, and associated scripts.

## Core Entity Attributes

The `Entity` tag defines the fundamental properties of the fly nest.

*   **`name`**: "unknown" (This is a placeholder and might be intended to be more specific).
*   **`tags`**: A comma-separated list of tags that define the entity's behavior and interactions:
    *   `mortal`: The entity can be killed.
    *   `nest`: Identifies it as a nest structure.
    *   `predator`: Indicates it's a predator in the game's ecosystem.
    *   `hittable`: The entity can be targeted and damaged.
    *   `glue_NOT`: This tag suggests it's not affected by glue in a specific way.

## DamageModelComponent

This component governs how the fly nest takes damage and its reactions.

*   **`hp`**: 5 (Hit Points)
*   **`max_hp`**: 5 (Maximum Hit Points)
*   **`falling_damage_damage_max`**: 1.2 (Maximum damage from falling)
*   **`falling_damage_height_min`**: 70 (Minimum height for falling damage to apply)
*   **`fire_damage_amount`**: 0.2 (Damage taken per second from fire)
*   **`fire_probability_of_ignition`**: 0.5 (50% chance to ignite when exposed to fire)
*   **`materials_that_damage`**: A list of materials that inflict damage upon contact: `acid,lava,poison,blood_cold,blood_cold_vapour`.
*   **`materials_how_much_damage`**: The corresponding damage values for each material in `materials_that_damage`.
*   **`drop_items_on_death`**: 1 (Drops items when destroyed).
*   **`ragdoll_material`**: "nest\_box2d" (The material used for its ragdoll effect).

## GenomeDataComponent

This component defines the entity's role within the game's ecosystem.

*   **`food_chain_rank`**: 20 (Its position in the food chain).
*   **`herd_id`**: "nest" (Identifies it as part of a "nest" group).
*   **`is_predator`**: 1 (Confirms it's a predator).

## HitboxComponent

Defines the physical boundaries of the fly nest for collision detection.

*   **`aabb_max_x`**: 9.7143
*   **`aabb_max_y`**: -2.71429
*   **`aabb_min_x`**: -10.42857
*   **`aabb_min_y`**: -23

## LuaComponent

This component links the entity to its associated Lua script for custom behavior.

*   **`script_source_file`**: `data/scripts/buildings/flynest.lua` (The path to the script that controls its logic).
*   **`execute_every_n_frame`**: 121 (The script logic runs every 121 frames).
*   **`execute_times`**: -1 (The script will execute indefinitely).

## SpriteComponent

Defines the visual appearance of the fly nest.

*   **`image_file`**: `data/buildings_gfx/flynest.xml` (The XML file containing the sprite definitions).
*   **`offset_x`**: 0
*   **`offset_y`**: 0

## ParticleEmitterComponent

This component is responsible for emitting particles from the fly nest.

*   **`emitted_material_name`**: "honey" (The material of the emitted particles).
*   **`count_min`**: 1
*   **`count_max`**: 2 (Emits 1 to 2 particles per emission cycle).
*   **`offset.y`**: -5 (The particles are emitted slightly below the nest's center).
*   **`emission_interval_min_frames`**: 20
*   **`emission_interval_max_frames`**: 40 (Particles are emitted every 20 to 40 frames).
*   **`is_emitting`**: 1 (The particle emitter is active).

## ItemChestComponent

This component indicates that the fly nest can contain items.

*   **`item_count_min`**: 3
*   **`item_count_max`**: 4 (The nest will contain 3 to 4 items).
*   **`level`**: 3 (The quality or tier of items found within).