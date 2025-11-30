---
title: Wizard Swapper Entity
category: entities
---

# Wizard Swapper Entity

This document details the `wizard_swapper.xml` entity, an illusionary enemy in Noita. It's designed to be a disruptive force, capable of swapping positions with the player.

## Core Components

The Wizard Swapper utilizes a variety of components to define its behavior, appearance, and interactions.

### Base Entity

The entity inherits from `base_enemy_basic.xml`, providing fundamental enemy properties.

### AnimalAIComponent

This component governs the AI and combat behavior of the Wizard Swapper.

*   **`creature_detection_range_x` / `creature_detection_range_y`**: Sets the detection radius for creatures (400 units).
*   **`sense_creatures`**: Enabled (1), allowing it to perceive other creatures.
*   **`attack_ranged_enabled`**: Enabled (1), indicating it can perform ranged attacks.
*   **`can_fly`**: Enabled (1), allowing flight.
*   **`attack_ranged_entity_file`**: Specifies the projectile used for its ranged attack: `data/entities/projectiles/orb_swapper.xml`.
*   **`attack_ranged_frames_between`**: The cooldown between ranged attacks (180 frames).
*   **`attack_ranged_max_distance`**: The maximum range for its ranged attack (300 units).

### SpriteComponent

Defines the visual appearance of the entity.

*   **`image_file`**: The primary sprite file: `data/enemies_gfx/wizard_swapper.xml`.
*   **`alpha`**: Initial transparency (0.5).

A second `SpriteComponent` with `_tags="character"` and `emissive="1"` is used for its glowing, emissive effect, with `image_file="data/enemies_gfx/wizard_tele_emissive.xml"`.

### LuaComponent

Scripts that add custom functionality.

*   **`script_damage_received`**: `data/scripts/animals/wizard_swapper_damage.lua` handles damage taken by the entity.
*   **`script_source_file`**: `data/scripts/animals/illusion_disappear.lua` controls its disappearance behavior.

### GenomeDataComponent

Defines its place in the ecosystem.

*   **`herd_id`**: "ghost"
*   **`food_chain_rank`**: 6
*   **`is_predator`**: 1

### CharacterPlatformingComponent

Controls movement and physics.

*   **`jump_velocity_y`**: The vertical force applied when jumping (-12).
*   **`run_velocity`**: The horizontal movement speed (18).

### LifetimeComponent

*   **`lifetime`**: The entity's lifespan in frames (600).

## Key Attributes

| Attribute                     | Value                                       | Description                                                                 |
| :---------------------------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `name`                        | `$animal_wizard_swapper`                    | Internal name for the entity.                                               |
| `tags`                        | `glue_NOT`                                  | Prevents the entity from being affected by glue.                            |
| `attack_ranged_entity_file`   | `data/entities/projectiles/orb_swapper.xml` | The projectile fired by the Wizard Swapper.                                 |
| `can_fly`                     | `1`                                         | Allows the entity to fly.                                                   |
| `sense_creatures`             | `1`                                         | Enables the entity to detect other creatures.                               |
| `script_damage_received`      | `data/scripts/animals/wizard_swapper_damage.lua` | Custom script for handling damage events.                                   |
| `script_source_file`          | `data/scripts/animals/illusion_disappear.lua` | Custom script for managing the entity's disappearance.                      |
| `image_file` (SpriteComponent) | `data/enemies_gfx/wizard_swapper.xml`       | The main visual asset for the entity.                                       |
| `emissive` (SpriteComponent)  | `1`                                         | Makes the entity's sprite glow.                                             |
| `lifetime`                    | `600`                                       | The duration the entity exists before despawning.                           |

## Audio Components

The entity has several audio components for its movement and general sounds.

*   **`AudioLoopComponent`**: Plays a looping movement sound (`animals/wizard/movement_loop`).
*   **`AudioComponent`**: Plays general wizard sounds (`animals/wizard`).
*   **`AudioComponent`**: Plays illusion-specific sounds (`animals/illusion`).

## Other Notable Components

*   **`ItemChestComponent`**: Indicates it can drop loot (level 2).
*   **`PathFindingComponent`**: Enables pathfinding capabilities.
*   **`CameraBoundComponent`**: Manages its visibility based on camera distance.
*   **`HitboxComponent`**: Defines its collision area (though disabled by default in the base).
*   **`CharacterDataComponent`**: Specifies its collision bounding box.
*   **`HotspotComponent`**: Used for attaching other elements, like capes.