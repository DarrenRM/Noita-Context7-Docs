---
title: Stonestone Item
category: entities
---

# Stonestone Item

This document details the configuration of the "Stonestone" item entity in Noita, focusing on its properties and behaviors relevant to modding.

## Core Entity Properties

The `stonestone.xml` file defines an item with several key tags that dictate its fundamental behavior:

*   `hittable`: Allows the item to be damaged or affected by projectiles.
*   `teleportable_NOT`: Prevents the item from being teleported.
*   `item_physics`: Indicates the item has physical properties and interacts with the game world.
*   `item_pickup`: Marks it as an item that can be picked up by the player.
*   `stonestone`: A custom tag for this specific item.

## Base Item Configuration

The item inherits its base functionality from `data/entities/base_item_projectile.xml`.

### Projectile Component

*   `damage_by_type`: Defines damage multipliers for different damage types.
    *   `radioactive`: 0.5 (deals half radioactive damage).

## Physical Properties

### Physics Body Component

This component governs the item's physical presence in the world.

*   `uid`: Unique identifier (1).
*   `allow_sleep`: `1` (allows the physics body to go to sleep when inactive).
*   `is_bullet`: `1` (treats it as a projectile for physics calculations).
*   `on_death_leave_physics_body`: `1` (leaves a physics body behind when destroyed).
*   `hax_fix_going_through_ground`: `1` (a fix for potential ground clipping issues).

### Physics Image Shape Component

Defines the visual shape and material of the item's physical body.

*   `image_file`: `data/items_gfx/stonestone.png` (the sprite used for its physical form).
*   `material`: `rock_box2d_hard` (determines its interaction with other physics objects).

### Physics Throwable Component

Controls how the item behaves when thrown.

*   `max_throw_speed`: `180`
*   `throw_force_coeff`: `1.5`

### Velocity Component

Manages the item's velocity.

*   `_tags="enabled_in_world"`: Active when in the game world.

## Item Specifics

### Sprite Component

Defines the visual representation of the item when held or in the inventory.

*   `image_file`: `data/items_gfx/stonestone.png`
*   `offset_x`: `4`
*   `offset_y`: `4`

### Item Component

Core properties for the item's identity and interaction.

*   `item_name`: `$item_stonestone` (references a localization string for the item's name).
*   `ui_description`: `$itemdesc_stonestone` (references a localization string for its description).
*   `ui_sprite`: `data/ui_gfx/items/stonestone.png` (the sprite used in UI elements like the inventory).
*   `is_pickable`: `1` (can be picked up by the player).
*   `is_equipable_forced`: `1` (can be equipped directly).
*   `preferred_inventory`: `QUICK` (defaults to the quick inventory slot).

### UI Info Component

Provides information for the user interface.

*   `name`: `$item_stonestone`

### Ability Component

Grants abilities to the item.

*   `throw_as_item`: `1` (allows it to be thrown as an item).
*   `gun_config`:
    *   `deck_capacity`: `0` (not a wand with a deck).

## Visual Effects and Particles

### Sprite Particle Emitter Component

Responsible for visual effects, likely when the item is active or interacting.

*   `sprite_file`: `data/particles/ray.xml`
*   `lifetime`: `1.5`
*   `color.r`, `color.g`, `color.b`, `color.a`: Defines the initial color.
*   `color_change.a`: `-3.5` (alpha fades out).
*   `scale_velocity.x`, `scale_velocity.y`: Controls scaling over time.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls particle emission rate.
*   `emissive`, `additive`: Affects how particles are rendered.
*   `use_velocity_as_rotation`: `1` (particles orient based on their velocity).
*   `randomize_position`, `randomize_velocity`: Adds variation to particle spawn and movement.
*   `velocity_always_away_from_center`: `1` (particles move outwards).

### Light Component (x2)

These components add light sources to the item.

*   **Primary Light:**
    *   `radius`: `130`
    *   `fade_out_time`: `1.5`
    *   `r`, `g`, `b`: `240`, `180`, `120` (warm, yellowish light).
*   **Secondary Light:**
    *   `radius`: `16`
    *   `fade_out_time`: `1.5`
    *   `r`, `g`, `b`: `255`, `255`, `255` (bright white light).

### Particle Emitter Component (x3)

These components manage the emission of various particles.

*   **Soil Particle Emitter 1 (World/Hand):**
    *   `emitted_material_name`: `soil`
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Controls particle velocity.
    *   `gravity.y`: `35`
    *   `friction`: `0.1`
    *   `count_min`, `count_max`: Number of particles emitted.
    *   `lifetime_min`, `lifetime_max`: Duration of particles.
    *   `collide_with_grid`, `render_on_grid`: Particles interact with the game grid.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Emission rate.
    *   `is_emitting`: `1` (actively emits particles).

*   **Soil Particle Emitter 2 (World/Hand - Cosmetic):**
    *   Similar to the first soil emitter but configured for cosmetic particles (`emit_cosmetic_particles="1"`).
    *   Higher `emission_interval_max_frames` suggests a less frequent emission.

*   **Spark Particle Emitter (Inventory/Hand):**
    *   `emitted_material_name`: `spark_red`
    *   `gravity.y`: `0` (no gravity).
    *   `count_min`, `count_max`: `1`, `2`
    *   `is_trail`: `0`
    *   `fade_based_on_lifetime`: `1`
    *   `lifetime_min`, `lifetime_max`: `0.8`, `2.0`
    *   `airflow_force`, `airflow_time`, `airflow_scale`: Controls air interaction.
    *   `emit_cosmetic_particles`: `1`
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `2`, `5` (frequent emission).

## Scripting

### Lua Component

Links a Lua script to the entity for custom logic.

*   `script_kick`: `data/scripts/items/stonestone.lua` (the path to the associated script file).
*   `execute_every_n_frame`: `-1` (indicates the script is likely triggered by events rather than a fixed frame rate).

## Magic Conversion (Disabled by Default)

### Magic Convert Material Component

This component is present but disabled (`_enabled="0"`). If enabled, it would allow the item to convert materials.

*   `kill_when_finished`: `0` (does not destroy itself after conversion).
*   `steps_per_frame`: `3`
*   `from_material_tag`: `[earth]` (converts materials tagged as "earth").
*   `to_material`: `soil` (converts to "soil").
*   `is_circle`: `1` (conversion area is circular).
*   `radius`: `48`
*   `reaction_audio_amount`: `0.005` (controls the volume of audio feedback).