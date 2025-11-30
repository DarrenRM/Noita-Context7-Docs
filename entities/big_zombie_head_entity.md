---
title: Big Zombie Head Entity
category: entities
---

# Big Zombie Head Entity

This document details the `bigzombiehead.xml` entity, a flying zombie variant in Noita.

## Core Components

### Base Entity

The `bigzombiehead` inherits its core functionality from `data/entities/base_enemy_flying.xml`.

### AnimalAIComponent

This component governs the AI behavior of the Big Zombie Head.

*   **`attack_ranged_enabled`**: `0` - This entity does not use ranged attacks.
*   **`attack_melee_enabled`**: `1` - Capable of melee combat.
*   **`attack_dash_enabled`**: `1` - Can perform a dash attack.
*   **`attack_melee_damage_min`**: `0.5` - Minimum melee damage.
*   **`attack_melee_damage_max`**: `0.6` - Maximum melee damage.
*   **`eye_offset_y`**: `-8` - Vertical offset for its eyes.
*   **`aggressiveness_min`**: `1` - Minimum aggressiveness level.
*   **`aggressiveness_max`**: `50` - Maximum aggressiveness level.
*   **`needs_food`**: `0` - Does not require food.
*   **`can_fly`**: `1` - This entity can fly.

### DamageModelComponent

Defines the health and damage resistances of the entity.

*   **`hp`**: `4` - The entity has 4 hit points.
*   **`fire_probability_of_ignition`**: `0` - Cannot be ignited by fire.
*   **`ragdoll_material`**: `meat_cursed` - The material used for its ragdoll.
*   **`ragdoll_filenames_file`**: `data/ragdolls/bigzombie/filenames_head.txt` - Specifies the ragdoll sprite files.

#### Damage Multipliers

*   **`holy`**: `1.2` - Takes 20% more damage from holy sources.

### PathFindingComponent

Determines how the entity navigates the environment.

*   **`can_fly`**: `1` - Can navigate through the air.
*   **`can_walk`**: `0` - Cannot walk on ground surfaces.

### SpriteComponent

Handles the visual representation of the entity.

*   **`image_file`**: `data/enemies_gfx/bigzombiehead.xml` - Points to the sprite definition file.
*   **`offset_x`**: `0` - No horizontal offset for the sprite.
*   **`offset_y`**: `0` - No vertical offset for the sprite.

### HitboxComponent

Defines the collision area for the entity.

*   **`aabb_min_x`**: `-2.5` - Minimum X-axis boundary of the hitbox.
*   **`aabb_max_x`**: `2.5` - Maximum X-axis boundary of the hitbox.
*   **`aabb_min_y`**: `-16.0` - Minimum Y-axis boundary of the hitbox.
*   **`aabb_max_y`**: `-8` - Maximum Y-axis boundary of the hitbox.
*   **`is_enemy`**: `1` - This hitbox belongs to an enemy.
*   **`is_item`**: `0` - Not an item.
*   **`is_player`**: `0` - Not the player.

### GenomeDataComponent

Relates to the entity's genetic properties and herd behavior.

*   **`herd_id`**: `zombie` - Identifies this entity as part of the "zombie" herd.

### CharacterDataComponent

Defines physical characteristics like collision and mass.

*   **`collision_aabb_min_x`**: `-4.5` - Minimum X-axis boundary for character collision.
*   **`collision_aabb_max_x`**: `4.5` - Maximum X-axis boundary for character collision.
*   **`collision_aabb_min_y`**: `-14` - Minimum Y-axis boundary for character collision.
*   **`collision_aabb_max_y`**: `-7` - Maximum Y-axis boundary for character collision.
*   **`mass`**: `0.4` - The mass of the character.

## Scripting

### LuaComponent

Attaches Lua scripts to the entity.

*   **`script_death`**: `data/scripts/animals/bigzombiehead.lua` - This script is executed when the entity dies.
*   **`execute_every_n_frame`**: `-1` - The script is not executed on a frame-by-frame basis.
*   **`remove_after_executed`**: `0` - The entity is not removed after the script executes.