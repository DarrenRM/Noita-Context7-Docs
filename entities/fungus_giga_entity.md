---
title: Fungus Giga Entity
category: entities
---

# Fungus Giga Entity

This document details the `fungus_giga.xml` entity, a large, aggressive fungal creature in Noita. It focuses on its combat capabilities, movement, and unique properties.

## Core Attributes

The Fungus Giga is a formidable enemy with several key attributes that define its behavior and threat level.

### `Base` Entity Inheritance

The Fungus Giga inherits from `base_enemy_basic.xml`, gaining fundamental enemy properties.

### `AnimalAIComponent`

This component governs the creature's artificial intelligence and combat actions.

*   **`escape_if_damaged_probability`**: `20` - Has a 20% chance to attempt to flee when damaged.
*   **`food_material`**: `blood` - Indicates its predatory nature, consuming blood.
*   **`attack_melee_enabled`**: `0` - Melee attacks are disabled.
*   **`attack_dash_enabled`**: `1` - Capable of a dashing attack.
*   **`attack_dash_lob`**: `1.3` - Controls the trajectory or arc of the dash.
*   **`attack_ranged_enabled`**: `1` - Can perform ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/pollen_ball.xml` - Fires `pollen_ball.xml` projectiles.
*   **`attack_ranged_frames_between`**: `120` - Ranged attacks have a cooldown of 120 frames.
*   **`aggressiveness_min`**: `10`
*   **`aggressiveness_max`**: `100` - High aggressiveness range.
*   **`attack_dash_damage`**: `1.4` - Dash attack deals 1.4 times base damage.

### `DamageModelComponent`

Defines the creature's health, resistances, and how it reacts to damage.

*   **`hp`**: `16.6` - Health points.
*   **`fire_probability_of_ignition`**: `20` - 20% chance to ignite.
*   **`ragdoll_material`**: `fungus_loose_trippy` - The material used for its ragdoll.
*   **`blood_material`**: `blood_fungi` - The material of its blood.
*   **`blood_sprite_directional`**: `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` - Uses purple directional blood splatters.
*   **`blood_sprite_large`**: `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` - Uses large purple blood splatters.
*   **`minimum_knockback_force`**: `100000` - Requires significant force to knock back.
*   **`damage_multipliers`**:
    *   `fire`: `1.4` - Takes 40% more damage from fire.
    *   `explosion`: `0.0` - Immune to explosion damage.

### `SpriteComponent`

Specifies the visual representation of the Fungus Giga.

*   **`image_file`**: `data/enemies_gfx/fungus_giga.xml` - Uses a specific sprite definition.

### `PathFindingComponent`

Determines how the creature navigates the game world.

*   **`frames_to_get_stuck`**: `120` - Takes 120 frames to be considered stuck.
*   **`can_jump`**: `1` - Capable of jumping.
*   **`never_consider_line_of_sight`**: `1` - Ignores line of sight for pathfinding.

### `GenomeDataComponent`

Defines its place in the ecosystem.

*   **`herd_id`**: `fungus` - Belongs to the "fungus" herd.
*   **`food_chain_rank`**: `15` - High rank in the food chain.
*   **`is_predator`**: `1` - Is a predator.

### `CharacterPlatformingComponent`

Controls movement parameters.

*   **`jump_velocity_y`**: `-18` - Jump strength.
*   **`run_velocity`**: `14` - Movement speed.

### `HitboxComponent`

Defines the collision area for interactions.

*   **`aabb_max_x`**: `6`
*   **`aabb_max_y`**: `4`
*   **`aabb_min_x`**: `-6`
*   **`aabb_min_y`**: `-24`

### `CharacterDataComponent`

Further defines physical properties.

*   **`collision_aabb_min_x`**: `-4.0`
*   **`collision_aabb_max_x`**: `4.0`
*   **`collision_aabb_min_y`**: `-14`
*   **`collision_aabb_max_y`**: `3`
*   **`mass`**: `1.3`

## Special Components

These components add unique mechanics and behaviors to the Fungus Giga.

### `MaterialInventoryComponent`

Manages the materials the creature possesses and can drop or leak.

*   **`leak_on_damage_percent`**: `0.999` - Leaks almost all its material when critically damaged.
*   **`count_per_material_type`**:
    *   `Material material="blood_fungi" count="400"` - Contains 400 units of `blood_fungi`.

### `LuaComponent` (Death Script)

*   **`script_death`**: `data/scripts/animals/fungus_big_death.lua` - Executes a custom script upon death.

### `LuaComponent` (Pollen Script)

*   **`script_source_file`**: `data/scripts/animals/fungus_giga_pollen.lua` - Runs a script related to pollen generation.
*   **`execute_every_n_frame`**: `10` - The pollen script executes every 10 frames.

### `ParticleEmitterComponent`

Responsible for emitting particles.

*   **`emitted_material_name`**: `acid_gas` - Emits `acid_gas`.
*   **`lifetime_min`**: `0.6`
*   **`lifetime_max`**: `1.8`
*   **`emission_interval_min_frames`**: `2`
*   **`emission_interval_max_frames`**: `8`
*   **`is_emitting`**: `1` - Actively emitting particles.

### `Entity` with `GameEffectComponent`

This nested entity grants a special effect.

*   **`effect`**: `PROTECTION_EXPLOSION` - Grants immunity to explosions.
*   **`frames`**: `-1` - The effect is permanent.