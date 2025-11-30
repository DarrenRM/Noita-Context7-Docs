---
title: Ice Skull Enemy Entity
category: entities
---

# Ice Skull Enemy Entity

This document details the configuration of the Ice Skull enemy entity in Noita, focusing on its key attributes for AI-assisted modding.

## Core Entity Configuration

The Ice Skull is a flying enemy with distinct offensive and defensive capabilities.

### Base Entity Properties

*   **`Base file="data/entities/base_enemy_flying.xml"`**: Inherits core flying enemy behaviors and properties.
*   **`ItemChestComponent level="2"`**: Indicates it can drop loot of level 2 rarity.

### AI and Combat Behavior (`AnimalAIComponent`)

This component governs the Ice Skull's movement and attack patterns.

*   **`attack_ranged_entity_file="data/entities/projectiles/ice.xml"`**: Specifies the projectile used for ranged attacks.
*   **`attack_ranged_enabled="1"`**: Enables ranged attacks.
*   **`attack_dash_enabled="1"`**: Enables a dash attack.
*   **`attack_ranged_frames_between="40"`**: Cooldown between ranged attacks.
*   **`attack_ranged_max_distance="80"`**: Maximum range for ranged attacks.
*   **`needs_food="0"`**: The entity does not require food to survive.
*   **`can_fly="1"`**: The entity is capable of flight.

### Damage and Material Properties (`DamageModelComponent`)

Defines the entity's health, resistances, and how it interacts with damage types.

*   **`hp="1.5"`**: The entity's health points.
*   **`materials_that_damage`**: Lists materials that inflict damage to the Ice Skull.
    *   `acid,lava,poison,radioactive_gas,radioactive_gas_static,rock_static_radioactive`
*   **`materials_how_much_damage`**: Corresponding damage multipliers for the materials listed above.
    *   `0.004,0.004,0.001,0.001,0.001,0.001`
*   **`ragdoll_filenames_file="data/ragdolls/iceskull/filenames.txt"`**: Points to the file defining its ragdoll physics.
*   **`ragdoll_material="ice_b2"`**: The material used for its ragdoll.
*   **`blood_material="blood_cold"`**: The material used for its blood.
*   **`fire_probability_of_ignition="0"`**: Cannot be ignited by fire.
*   **`damage_multipliers`**:
    *   **`ice="0.0"`**: Immune to ice damage.

### Movement and Collision (`PathFindingComponent`, `HitboxComponent`, `CharacterDataComponent`)

These components define how the entity navigates and interacts physically with the game world.

*   **`PathFindingComponent`**:
    *   **`can_fly="1"`**: Can navigate through the air.
    *   **`can_walk="0"`**: Cannot walk on ground.
*   **`HitboxComponent`**:
    *   **`aabb_min_x="-4.5"`, `aabb_max_x="4.5"`**: Defines the horizontal bounds of its hitbox.
    *   **`aabb_min_y="-12"`, `aabb_max_y="1"`**: Defines the vertical bounds of its hitbox.
*   **`CharacterDataComponent`**:
    *   **`mass="0.4"`**: The entity's mass.
    *   **`collision_aabb_min_x="-2.0"`, `collision_aabb_max_x="2.0"`**: Defines the horizontal bounds for collision detection.
    *   **`collision_aabb_min_y="-10"`, `collision_aabb_max_y="0"`**: Defines the vertical bounds for collision detection.

### Visuals (`SpriteComponent`)

*   **`image_file="data/enemies_gfx/iceskull.xml"`**: Specifies the graphical assets for the Ice Skull.

### Genetic Information (`GenomeDataComponent`)

*   **`herd_id="ice"`**: Identifies this entity as part of the "ice" herd for genetic purposes.

## Special Components

### Light Component (`LightComponent`)

*   **`radius="30"`**: The radius of the light emitted.
*   **`r="100"`, `g="160"`, `b="255"`**: Defines the light color as a pale blue.

### Particle Emitters (`ParticleEmitterComponent`)

The Ice Skull has two particle emitters, both emitting `blood_cold_vapour`.

**Emitter 1 (General):**
*   **`emitted_material_name="blood_cold_vapour"`**: The type of particle emitted.
*   **`count_min="1"`, `count_max="3"`**: Number of particles per emission burst.
*   **`lifetime_min="0.4"`, `lifetime_max="1.0"`**: Duration particles exist.
*   **`emission_interval_min_frames="3"`, `emission_interval_max_frames="6"`**: Frequency of emissions.
*   **`is_emitting="1"`**: The emitter is active.

**Emitter 2 (Custom Style):**
*   **`custom_style="FIRE"`**: Applies a specific visual style to the particles.
*   **`color="ff50e7f0"`**: Custom color for these particles.
*   **`count_min="4"`, `count_max="9"`**: Number of particles per emission burst.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`**: Higher frequency of emissions.

### Lua Scripting (`LuaComponent`)

*   **`script_damage_received="data/scripts/animals/iceskull_damage.lua"`**: Links a custom Lua script to handle damage events for this entity.

### Audio (`AudioLoopComponent`, `AudioComponent`)

*   **`AudioLoopComponent`**: Manages the looping movement sound.
    *   **`file="data/audio/Desktop/animals.bank"`**: Audio bank file.
    *   **`event_name="animals/iceskull/movement_loop"`**: Specific sound event for movement.
    *   **`auto_play="1"`**: Sound plays automatically.
*   **`AudioComponent`**: Manages other general sound events.
    *   **`file="data/audio/Desktop/animals.bank"`**: Audio bank file.
    *   **`event_root="animals/iceskull"`**: Root event name for sounds related to the Ice Skull.