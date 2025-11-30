---
title: Big Zombie Torso Entity
category: entities
---

# Big Zombie Torso Entity

This document details the `bigzombietorso.xml` entity, representing a basic enemy type in Noita.

## Core Attributes

The `bigzombietorso` entity is a foundational enemy with several key components that define its behavior and appearance.

### `Entity`

*   **`name`**: `$animal_bigzombie` - Internal identifier for the entity.
*   **`tags`**: `zombie` - Categorizes the entity for game logic.

### `Base` (Inherited from `base_enemy_basic.xml`)

This section outlines the primary AI and combat behaviors.

#### `AnimalAIComponent`

*   **`_enabled`**: `1` - Enables the AI component.
*   **`preferred_job`**: `JobDefault` - The default behavior assigned to this creature.
*   **`escape_if_damaged_probability`**: `0` - This zombie does not attempt to flee when damaged.
*   **`attack_melee_action_frame`**: `3` - The frame at which a melee attack is executed.
*   **`attack_melee_damage_min`**: `0.6` - Minimum damage dealt by a melee attack.
*   **`attack_melee_damage_max`**: `0.8` - Maximum damage dealt by a melee attack.
*   **`attack_dash_enabled`**: `1` - The zombie can perform a dash attack.
*   **`creature_detection_range_x`**: `300` - Horizontal range for detecting other creatures.
*   **`creature_detection_range_y`**: `300` - Vertical range for detecting other creatures.
*   **`food_material`**: `meat` - The material this creature considers food.
*   **`needs_food`**: `0` - This zombie does not require food to survive.
*   **`sense_creatures`**: `1` - The zombie can detect nearby creatures.
*   **`attack_ranged_enabled`**: `1` - The zombie can perform ranged attacks.
*   **`attack_ranged_entity_file`**: `data/entities/projectiles/fireball.xml` - The projectile entity used for ranged attacks.
*   **`attack_ranged_frames_between`**: `40` - Delay in frames between ranged attacks.
*   **`attack_ranged_action_frame`**: `4` - The frame at which a ranged attack is executed.
*   **`can_fly`**: `0` - The zombie cannot fly.
*   **`defecates_and_pees`**: `1` - The zombie has bodily functions.
*   **`aggressiveness_min`**: `1` - Minimum aggressiveness level.
*   **`aggressiveness_max`**: `50` - Maximum aggressiveness level.

#### `DamageModelComponent`

*   **`hp`**: `6` - The zombie's health points.
*   **`materials_create_messages`**: `1` - When damaged, it creates messages.
*   **`ragdoll_material`**: `meat_cursed` - The material used for its ragdoll.
*   **`ragdoll_filenames_file`**: `data/ragdolls/bigzombie/filenames_torso.txt` - Specifies the files for its ragdoll.
*   **`damage_multipliers`**:
    *   **`holy`**: `1.2` - Takes 20% more damage from holy sources.

#### `SpriteComponent`

*   **`image_file`**: `data/enemies_gfx/bigzombietorso.xml` - The graphical asset file for the zombie's sprite.
*   **`offset_x`**: `0` - Horizontal offset for the sprite.
*   **`offset_y`**: `0` - Vertical offset for the sprite.

#### `PathFindingComponent`

*   **`distance_to_reach_node_x`**: `20` - Horizontal distance to consider a path node reached.
*   **`distance_to_reach_node_y`**: `20` - Vertical distance to consider a path node reached.
*   **`can_swim_on_surface`**: `1` - Can swim on the surface of liquids.
*   **`can_dive`**: `1` - Can dive into liquids.
*   **`frames_to_get_stuck`**: `1` - How many frames it takes to be considered stuck.
*   **`can_jump`**: `1` - The zombie can jump.

#### `CharacterDataComponent`

*   **`collision_aabb_min_x`**: `-4.0` - Minimum X-coordinate for collision bounding box.
*   **`collision_aabb_max_x`**: `3.0` - Maximum X-coordinate for collision bounding box.
*   **`collision_aabb_min_y`**: `-8` - Minimum Y-coordinate for collision bounding box.
*   **`collision_aabb_max_y`**: `3` - Maximum Y-coordinate for collision bounding box.
*   **`buoyancy_check_offset_y`**: `-4` - Vertical offset for buoyancy checks.
*   **`mass`**: `1.7` - The mass of the zombie.

#### `CharacterPlatformingComponent`

*   **`pixel_gravity`**: `500` - The strength of gravity applied to the character.
*   **`jump_velocity_y`**: `-12` - The vertical velocity applied when jumping.
*   **`run_velocity`**: `22` - The horizontal movement speed.

#### `HitboxComponent`

*   **`aabb_min_x`**: `-4.5` - Minimum X-coordinate for the hitbox.
*   **`aabb_max_x`**: `4.5` - Maximum X-coordinate for the hitbox.
*   **`aabb_min_y`**: `-6.5` - Minimum Y-coordinate for the hitbox.
*   **`aabb_max_y`**: `3` - Maximum Y-coordinate for the hitbox.
*   **`is_enemy`**: `1` - This hitbox belongs to an enemy.
*   **`is_item`**: `0` - This hitbox is not an item.
*   **`is_player`**: `0` - This hitbox is not the player.

#### `CameraBoundComponent`

*   **`max_count`**: `20` - Maximum number of this entity that can be active within camera bounds.
*   **`distance`**: `160000` - The distance from the camera within which the entity is considered active.

### `ItemPickUpperComponent`

*   **`is_in_npc`**: `1` - Indicates this component is used when the entity is acting as an NPC.