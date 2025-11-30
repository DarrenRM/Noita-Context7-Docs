---
title: Ultimate Killer Entity
category: entities
---

# Ultimate Killer Entity

This document details the configuration of the "Ultimate Killer" entity in Noita, focusing on its AI, combat, and physical attributes for modding purposes.

## Core Attributes

The Ultimate Killer is a flying, aggressive creature with both melee and ranged attack capabilities. It is designed to be a challenging enemy.

### `Entity` Root Attributes

*   **`name`**: `$animal_ultimate_killer` - The internal identifier for this entity.
*   **`tags`**: `small_friend` - Indicates its classification within the game's entity system.

### `Base` Entity Configuration

The entity inherits core functionality from `data/entities/base_enemy_flying.xml`.

#### `AnimalAIComponent` - AI and Behavior

This component governs the creature's intelligence, detection, and combat actions.

*   **`preferred_job`**: `JobDefault` - The default behavior state.
*   **`escape_if_damaged_probability`**: `40` - 40% chance to attempt escape when damaged.
*   **`creature_detection_range_x`**: `400`
*   **`creature_detection_range_y`**: `400`
*   **`creature_detection_angular_range_deg`**: `60` - Defines the cone of vision for detecting other creatures.
*   **`food_material`**: `meat` - What it consumes.
*   **`needs_food`**: `1` - Requires food to survive.
*   **`sense_creatures`**: `1` - Actively senses nearby creatures.
*   **`can_fly`**: `1` - Capable of flight.
*   **`attack_melee_enabled`**: `1` - Melee attacks are active.
*   **`attack_melee_max_distance`**: `10` - Maximum range for melee attacks.
*   **`attack_ranged_enabled`**: `1` - Ranged attacks are active.
*   **`attack_ranged_action_frame`**: `2` - The frame at which the ranged attack is initiated.
*   **`attack_ranged_min_distance`**: `30` - Minimum range for ranged attacks.
*   **`attack_ranged_max_distance`**: `220` - Maximum range for ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/ultimate_killer_megabomb.xml` - The projectile spawned for ranged attacks.
*   **`attack_ranged_frames_between`**: `20` - Cooldown in frames between ranged attacks.
*   **`aggressiveness_min`**: `1`
*   **`aggressiveness_max`**: `80` - Determines how aggressive the creature is.

#### `DamageModelComponent` - Health and Damage Response

Manages the entity's health, resistances, and how it reacts to damage.

*   **`hp`**: `5.5` - Hit points.
*   **`materials_create_messages`**: `1` - Generates messages upon material interaction.
*   **`ragdoll_filenames_file`**: `data/ragdolls/ultimate_killer/filenames.txt` - Specifies ragdoll assets.
*   **`ragdoll_material`**: `meat_helpless` - The material of the ragdoll.
*   **`fire_probability_of_ignition`**: `5` - 5% chance to ignite from fire.
*   **`blood_spray_material`**: `blood` - The material used for blood effects.
*   **`damage_multipliers`**:
    *   **`holy`**: `0` - No multiplier for holy damage.

#### `SpriteComponent` - Visual Representation

Defines the visual assets and their positioning.

*   **`image_file`**: `data/enemies_gfx/ultimate_killer.xml` - The sprite sheet or animation definition.

#### `PathFindingComponent` - Movement and Navigation

Controls how the entity navigates the game world.

*   **`can_fly`**: `1` - Explicitly enables flight for pathfinding.
*   **`jump_speed`**: `80`
*   **`initial_jump_lob`**: `1`
*   **`initial_jump_max_distance_x`**: `60`
*   **`initial_jump_max_distance_y`**: `60`

#### `GenomeDataComponent` - Biological Classification

Provides information about the creature's place in the ecosystem.

*   **`herd_id`**: `orcs` - Group identifier.
*   **`food_chain_rank`**: `9` - Position in the food chain.
*   **`is_predator`**: `1` - Marked as a predator.

#### `CharacterPlatformingComponent` - Movement Physics

Fine-tunes the physics of movement, including flight.

*   **`fly_speed_change_spd`**: `0.8`
*   **`fly_velocity_x`**: `28` - Horizontal flight speed.
*   **`run_velocity`**: `17` - Ground movement speed.

#### `HitboxComponent` - Collision Detection

Defines the bounding box for physical interactions.

*   **`aabb_min_x`**: `-3`
*   **`aabb_max_x`**: `3`
*   **`aabb_min_y`**: `-5`
*   **`aabb_max_y`**: `3`

#### `CharacterDataComponent` - General Character Properties

Basic properties related to the character's physical form.

*   **`collision_aabb_min_x`**: `-2.0`
*   **`collision_aabb_max_x`**: `2.0`
*   **`collision_aabb_min_y`**: `-3`
*   **`collision_aabb_max_y`**: `3`
*   **`mass`**: `1.1`

## Additional Components

### `Entity` (Inherited Transform)

This nested entity applies a transform, likely for positioning attached components.

*   **`InheritTransformComponent`**:
    *   **`Transform position.x`**: `0`
    *   **`Transform position.y`**: `4`

### `LightComponent`

Adds a light source to the entity.

*   **`radius`**: `50`
*   **`fade_out_time`**: `1.5`

### `AudioComponent`

Manages sound effects for the entity.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_root`**: `animals/ultimate_killer`

### `LuaComponent`

Allows for custom Lua scripting.

*   **`script_death`**: `data/scripts/animals/ultimate_killer_death.lua` - Script executed upon death.

### `VariableStorageComponent`

Used for storing custom variables.

*   **`_tags`**: `no_gold_drop` - Indicates that this entity does not drop gold.