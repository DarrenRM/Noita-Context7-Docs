---
title: Fungus Big Entity
category: entities
---

# Fungus Big Entity

This document details the `fungus_big.xml` entity, a common enemy in Noita. It focuses on key attributes that define its behavior, appearance, and interactions.

## Base Entity Configuration

The `fungus_big` entity inherits from `base_enemy_basic.xml`, gaining fundamental enemy properties.

### Core Components

*   **ItemChestComponent**: Defines loot drops.
    *   `level`: 2 (Indicates a moderate tier of loot).
    *   `enemy_drop`: 1 (This enemy has a chance to drop items).

*   **AnimalAIComponent**: Governs AI behavior.
    *   `escape_if_damaged_probability`: 70 (70% chance to attempt escape when damaged).
    *   `food_material`: "blood" (Prefers blood as a food source).
    *   `attack_dash_enabled`: 1 (Can perform a dash attack).
    *   `attack_dash_lob`: 1.1 (Controls the trajectory of the dash attack).
    *   `aggressiveness_min`/`max`: 10/100 (Aggression level ranges from 10 to 100).

*   **DamageModelComponent**: Manages health and damage resistances/vulnerabilities.
    *   `hp`: 7.6 (Total health points).
    *   `ragdoll_material`: "fungus_loose_trippy" (Material used for its ragdoll).
    *   `blood_material`: "blood_fungi" (Type of blood it bleeds).
    *   `fire_probability_of_ignition`: 20 (20% chance to ignite from fire).
    *   `damage_multipliers`:
        *   `fire`: 2.0 (Takes double damage from fire).

*   **SpriteComponent**: Defines visual appearance.
    *   `image_file`: "data/enemies_gfx/fungus_big.xml" (Path to its sprite definition).

*   **PathFindingComponent**: Enables navigation.
    *   `can_jump`: 1 (Can jump over obstacles).
    *   `never_consider_line_of_sight`: 1 (Does not require line of sight for pathfinding, useful for navigating complex terrain).

*   **GenomeDataComponent**: Defines its place in the ecosystem.
    *   `herd_id`: "fungus" (Belongs to the "fungus" herd).
    *   `is_predator`: 1 (Acts as a predator).

*   **CharacterPlatformingComponent**: Controls movement parameters.
    *   `jump_velocity_y`: -18 (Vertical jump force).
    *   `run_velocity`: 14 (Horizontal movement speed).

*   **HitboxComponent**: Defines its collision area.
    *   `aabb_max_x`/`y`, `aabb_min_x`/`y`: Defines the bounding box for hit detection.

*   **CharacterDataComponent**: General character properties.
    *   `mass`: 1.3 (Its physical mass).

*   **AudioComponent**: Sound effects.
    *   `file`: "data/audio/Desktop/animals.bank"
    *   `event_root`: "animals/slime" (Base sound event for this entity).

## Additional Components

*   **MaterialInventoryComponent**: Manages internal materials.
    *   `leak_on_damage_percent`: 0.999 (Leaks almost all its internal material when heavily damaged).
    *   `count_per_material_type`:
        *   `Material material="blood_fungi" count="400"` (Contains 400 units of `blood_fungi`).

*   **LuaComponent**: Scripts for custom behavior.
    *   `script_death`: "data/scripts/animals/fungus_big_death.lua" (Script executed on death).
    *   `script_collision_trigger_hit`: "data/scripts/animals/fungus_smoke.lua" (Script executed when a collision trigger is hit).

*   **CollisionTriggerComponent**: Triggers events on collision.
    *   `timer_for_destruction`: 40 (When triggered, this entity will be destroyed after 40 frames).
    *   `required_tag`: "mortal" (Only triggers if the colliding entity has the "mortal" tag).

*   **ParticleEmitterComponent**: Spawns particles.
    *   `emitted_material_name`: "acid_gas" (Emits `acid_gas` particles).
    *   `emission_interval_min_frames`/`max_frames`: 2/10 (Emits particles periodically).
    *   `is_emitting`: 1 (Particle emission is active).

*   **AudioComponent**: Specific sound events for the fungus.
    *   `file`: "data/audio/Desktop/animals.bank"
    *   `event_root`: "animals/fungus" (Specific sound events for fungus-type creatures).