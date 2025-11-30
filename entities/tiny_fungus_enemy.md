---
title: Tiny Fungus Enemy
category: entities
---

# Tiny Fungus Enemy

This document details the configuration for the "Tiny Fungus" enemy entity in Noita, focusing on its AI, combat, and visual properties.

## Core Entity Configuration

The `fungus_tiny.xml` file defines a basic enemy with specific AI behaviors, damage properties, and visual assets.

### Base Enemy Properties

The entity inherits from `base_enemy_basic.xml`, providing foundational enemy functionalities.

*   **`ItemChestComponent`**: Configures loot drops.
    *   `level`: 2 (Indicates a moderate tier of loot).
    *   `enemy_drop`: 1 (Guaranteed drop from this enemy).

### AI Behavior (`AnimalAIComponent`)

This component governs the enemy's movement and combat logic.

*   **`_enabled`**: `1` (AI is active).
*   **`escape_if_damaged_probability`**: `70` (70% chance to attempt escape when damaged).
*   **`food_material`**: `blood` (AI targets blood as a resource/trigger).
*   **`attack_melee_enabled`**: `0` (Melee attacks are disabled).
*   **`attack_dash_enabled`**: `1` (Dash attack is enabled).
*   **`attack_dash_lob`**: `1.1` (Controls the arc/trajectory of the dash attack).
*   **`aggressiveness_min`**: `10`
*   **`aggressiveness_max`**: `100` (Determines how readily the AI engages).

### Damage and Health (`DamageModelComponent`)

Defines the entity's health, resistances, and how it reacts to damage.

*   **`hp`**: `1.6` (Low health pool).
*   **`air_needed`**: `0` (Does not require air to survive).
*   **`fire_probability_of_ignition`**: `100` (Highly susceptible to ignition).
*   **`ragdoll_material`**: `fungus_loose_trippy` (Material used for its ragdoll effect).
*   **`blood_material`**: `blood_fungi` (Material of the blood it spills).
*   **`blood_sprite_directional`**: `data/particles/bloodsplatters/bloodsplatter_directional_purple_$[1-3].xml` (Visuals for directional blood splatters).
*   **`blood_sprite_large`**: `data/particles/bloodsplatters/bloodsplatter_purple_$[1-3].xml` (Visuals for large blood splatters).
*   **`minimum_knockback_force`**: `100000` (High knockback resistance).
*   **`damage_multipliers`**:
    *   `fire`: `40.0` (Takes significantly increased damage from fire).

### Visuals (`SpriteComponent`)

Specifies the graphical assets for the entity.

*   **`image_file`**: `data/enemies_gfx/fungus_tiny_b.xml` (Path to the sprite definition).
*   **`offset_x`**, **`offset_y`**: `0` (No offset from the entity's origin).

### Pathfinding (`PathFindingGridMarkerComponent`, `PathFindingComponent`)

Components related to how the entity navigates the game world.

*   **`PathFindingGridMarkerComponent`**:
    *   `marker_work_flag`: `16` (Internal flag for pathfinding grid).
*   **`PathFindingComponent`**:
    *   `frames_to_get_stuck`: `120` (Number of frames before considering itself stuck).
    *   `can_jump`: `1` (Can jump over obstacles).
    *   `never_consider_line_of_sight`: `1` (Does not require line of sight to pathfind).

### Genetic Data (`GenomeDataComponent`)

Information related to the entity's place in the ecosystem.

*   **`herd_id`**: `fungus` (Identifies its group).
*   **`food_chain_rank`**: `15` (Position in the food chain).
*   **`is_predator`**: `1` (Classified as a predator).

### Movement (`CharacterPlatformingComponent`)

Defines basic movement parameters.

*   **`jump_velocity_y`**: `-12` (Vertical jump force).
*   **`run_velocity`**: `9` (Horizontal movement speed).

### Camera Bounds (`CameraBoundComponent`)

Controls how the entity interacts with the camera's view.

*   **`max_count`**: `30` (Maximum number of this entity that can be active within camera bounds).
*   **`distance`**: `160000` (Maximum distance from the camera before it's culled).

### Hitbox (`HitboxComponent`)

Defines the collision area for interactions.

*   **`aabb_max_x`**: `4`
*   **`aabb_max_y`**: `4`
*   **`aabb_min_x`**: `-4`
*   **`aabb_min_y`**: `-8` (Defines a rectangular bounding box).

### Character Data (`CharacterDataComponent`)

General character physics and collision properties.

*   **`collision_aabb_min_x`**: `-1.0`
*   **`collision_aabb_max_x`**: `1.0`
*   **`collision_aabb_min_y`**: `-6`
*   **`collision_aabb_max_y`**: `3` (Defines a tighter collision box for physics).
*   **`mass`**: `1.3` (Entity's mass).

### Audio (`AudioComponent`)

Defines sound events associated with the entity.

*   **`file`**: `data/audio/Desktop/animals.bank` (Sound bank file).
*   **`event_root`**: `animals/slime` (Base event name for sounds).

## Material Inventory (`MaterialInventoryComponent`)

Manages the materials contained within the entity.

*   **`_enabled`**: `1`
*   **`drop_as_item`**: `0` (Materials do not drop as a single item).
*   **`leak_on_damage_percent`**: `0.999` (Leaks almost all its material when heavily damaged).
*   **`count_per_material_type`**:
    *   `Material material="blood_fungi" count="400"` (Contains 400 units of `blood_fungi` material).

## Lua Scripting (`LuaComponent`)

Custom scripts that extend the entity's behavior.

*   **Death Script**:
    *   `script_death`: `data/scripts/animals/fungus_death.lua` (Executed when the entity dies).
*   **Collision Trigger Scripts**:
    *   `script_collision_trigger_timer_finished`: `data/scripts/animals/fungus_death.lua` (Executed when the collision trigger timer finishes).
    *   `script_collision_trigger_hit`: `data/scripts/animals/fungus_smoke.lua` (Executed when the collision trigger is hit).

## Collision Triggers (`CollisionTriggerComponent`)

Components that detect collisions and trigger events.

*   **Trigger 1**:
    *   `width`, `height`, `radius`: `10`, `10`, `5` (Defines the trigger area).
    *   `required_tag`: `player_unit` (Only triggers for player collisions).
    *   `timer_for_destruction`: `20` (Timer before destruction after trigger).
*   **Trigger 2**:
    *   `width`, `height`, `radius`: `10`, `10`, `5`
    *   `required_tag`: `player_unit`
    *   `timer_for_destruction`: `0` (Immediate effect).
    *   `destroy_this_entity_when_triggered`: `0` (Does not destroy the entity).
    *   `remove_component_when_triggered`: `1` (Removes this trigger component after activation).

## Particle Emitter (`ParticleEmitterComponent`)

Responsible for emitting particles.

*   **`emitted_material_name`**: `acid_gas` (The material of the emitted particles).
*   **`offset.x`, `offset.y`**: `0`
*   **`x_pos_offset_min/max`**, **`y_pos_offset_min/max`**: `-2` to `2` (Emission area).
*   **`x_vel_min/max`**, **`y_vel_min/max`**: `-10` to `10` (Particle velocity).
*   **`count_min/max`**: `1` to `2` (Number of particles per emission).
*   **`lifetime_min/max`**: `0.6` to `1.8` (Particle lifespan).
*   **`create_real_particles`**: `1` (Creates actual game particles).
*   **`emit_cosmetic_particles`**: `0` (Does not emit cosmetic particles).
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `10` to `35` (Delay between emissions).
*   **`is_emitting`**: `1` (Particle emission is active).

## Additional Audio (`AudioComponent`)

A second audio component, likely for specific fungus-related sounds.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_root`**: `animals/fungus`

## Variable Storage (`VariableStorageComponent`)

Used to store entity-specific variables.

*   **`_tags`**: `no_gold_drop` (Indicates that this entity will not drop gold).