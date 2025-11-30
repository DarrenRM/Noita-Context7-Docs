---
title: Sheep Bat Entity
category: entities
---

# Sheep Bat Entity

This document describes the `sheep_bat.xml` entity, a flying, prey animal in Noita.

## Core Components

The Sheep Bat is built upon a `base_helpless_animal.xml` entity, inheriting its fundamental behaviors.

### `AnimalAIComponent`

This component defines the AI and behavioral aspects of the Sheep Bat.

*   **`preferred_job`**: `Escaping` - The primary behavior is to flee from threats.
*   **`can_fly`**: `1` - The entity is capable of flight.
*   **`food_material`**: `grass` - While it needs food, it's not actively simulated in this entity.
*   **`needs_food`**: `0` - The entity does not require food to survive or act.
*   **`attack_melee_enabled`**: `0` - Cannot perform melee attacks.
*   **`attack_ranged_enabled`**: `0` - Cannot perform ranged attacks.

### `DamageModelComponent`

Handles damage and its effects on the entity.

*   **`hp`**: `0.3` - Very low health, making it fragile.
*   **`ragdoll_filenames_file`**: `data/ragdolls/sheep_bat/filenames.txt` - Specifies the ragdoll configuration for when it dies.
*   **`materials_create_messages`**: `1` - When damaged, it can create messages.
*   **`materials_that_create_messages`**: `grass` - Specifically, grass material can trigger messages upon damage.

### `SpriteComponent`

Defines the visual representation of the Sheep Bat.

*   **`image_file`**: `data/enemies_gfx/sheep_bat.xml` - Points to the sprite sheet and animation data.
*   **`offset_x`**: `10` - Horizontal offset for the sprite.
*   **`offset_y`**: `12` - Vertical offset for the sprite.

### `CharacterPlatformingComponent`

Governs movement and platforming capabilities.

*   **`run_velocity`**: `10` - The speed at which the entity moves.
*   **`jump_velocity_y`**: `0` - Cannot jump vertically.

### `PathFindingComponent`

Determines how the entity navigates the game world.

*   **`can_fly`**: `1` - Explicitly enables flight for pathfinding.
*   **`can_walk`**: `0` - Cannot walk on surfaces.
*   **`can_jump`**: `0` - Cannot jump.

### `HitboxComponent`

Defines the collision area for interactions.

*   **`aabb_max_x`**: `6`
*   **`aabb_max_y`**: `4`
*   **`aabb_min_x`**: `-6`
*   **`aabb_min_y`**: `-7`

### `CharacterDataComponent`

General character properties.

*   **`mass`**: `1.4` - The entity's mass.
*   **`collision_aabb_min_x`**: `-3.0`
*   **`collision_aabb_max_x`**: `3.0`
*   **`collision_aabb_min_y`**: `-6`
*   **`collision_aabb_max_y`**: `2`

### `GenomeDataComponent`

Provides genetic information for creature interactions.

*   **`herd_id`**: `helpless` - Identifies it as part of a "helpless" group.
*   **`food_chain_rank`**: `20` - Its position in the food chain.
*   **`is_predator`**: `0` - It is not a predator.

## Audio Components

The Sheep Bat has two audio components for sound effects.

*   **`AudioComponent` 1**:
    *   **`file`**: `data/audio/Desktop/animals.bank`
    *   **`event_root`**: `animals/sheep` - General sheep sounds.
*   **`AudioComponent` 2**:
    *   **`file`**: `data/audio/Desktop/animals.bank`
    *   **`event_root`**: `animals/wing_flap_skin` - Sounds related to wing flapping.