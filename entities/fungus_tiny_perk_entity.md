---
title: Fungus Tiny Perk Entity
category: entities
---

# Fungus Tiny Perk Entity

This document details the `fungus.xml` entity, which represents a "Fungus Tiny" perk in Noita. This entity is designed to be an enemy that can also function as a perk, likely by being collected or interacted with in a specific way.

## Core Components

### Base Entity Configuration

The entity inherits from `data/entities/base_enemy_basic.xml`, providing fundamental enemy behaviors.

### AI Component (`AnimalAIComponent`)

This component governs the entity's artificial intelligence and behavior.

| Attribute                  | Value                               | Description                                                                 |
| :------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                 | `1`                                 | Enables the AI component.                                                   |
| `escape_if_damaged_probability` | `70`                                | 70% chance to attempt to escape when damaged.                               |
| `food_material`            | `blood`                             | The material this entity considers as food.                                 |
| `attack_melee_enabled`     | `0`                                 | Melee attacks are disabled.                                                 |
| `attack_dash_enabled`      | `1`                                 | Dash attacks are enabled.                                                   |
| `attack_dash_lob`          | `1.1`                               | Controls the trajectory or arc of the dash attack.                          |
| `aggressiveness_min`       | `10`                                | Minimum aggressiveness level.                                               |
| `aggressiveness_max`       | `100`                               | Maximum aggressiveness level.                                               |

### Damage Component (`DamageModelComponent`)

Defines the entity's health, resistances, and how it reacts to damage.

| Attribute                  | Value                               | Description                                                                 |
| :------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                       | `10.6`                              | The entity's hit points.                                                    |
| `air_needed`               | `0`                                 | Does not require air to survive.                                            |
| `fire_probability_of_ignition` | `100`                               | 100% chance to ignite when exposed to fire.                                 |
| `ragdoll_material`         | `fungus_loose_trippy`               | The material used for its ragdoll when defeated.                            |
| `blood_material`           | `blood_fungi`                       | The material of blood it bleeds.                                            |
| `minimum_knockback_force`  | `100000`                            | A very high value, suggesting it's resistant to being knocked back.         |

#### Damage Multipliers

| Type  | Value | Description                               |
| :---- | :---- | :---------------------------------------- |
| `fire` | `40.0` | Takes 40x damage from fire.               |

### Sprite Component (`SpriteComponent`)

Determines the visual appearance of the entity.

| Attribute     | Value                               | Description                               |
| :------------ | :---------------------------------- | :---------------------------------------- |
| `image_file`  | `data/enemies_gfx/fungus_tiny.xml`  | Path to the sprite definition file.       |

### Pathfinding Components

These components enable the entity to navigate the game world.

*   **`PathFindingGridMarkerComponent`**: `marker_work_flag="16"` - Likely related to how it interacts with the navigation grid.
*   **`PathFindingComponent`**:
    *   `frames_to_get_stuck="120"`: Takes 120 frames before considering itself stuck.
    *   `can_jump="1"`: Can jump.
    *   `never_consider_line_of_sight="1"`: Ignores line of sight for pathfinding.

### Genome Data Component (`GenomeDataComponent`)

Defines its place in the game's ecosystem.

| Attribute         | Value   | Description                               |
| :---------------- | :------ | :---------------------------------------- |
| `herd_id`         | `player`| Associated with the player's herd.        |
| `food_chain_rank` | `15`    | Its position in the food chain.           |
| `is_predator`     | `1`     | It is a predator.                         |

### Character Platforming Component (`CharacterPlatformingComponent`)

Controls movement and jumping mechanics.

| Attribute        | Value | Description                               |
| :--------------- | :---- | :---------------------------------------- |
| `jump_velocity_y` | `-12` | The vertical velocity applied when jumping. |
| `run_velocity`    | `9`   | The horizontal movement speed.            |

### Hitbox and Collision Components

Define the physical boundaries for interaction and collision.

*   **`HitboxComponent`**: `aabb_max_x="4"`, `aabb_max_y="4"`, `aabb_min_x="-4"`, `aabb_min_y="-8"` - Defines the entity's primary hitbox.
*   **`CharacterDataComponent`**: `collision_aabb_min_x="-1.0"`, `collision_aabb_max_x="1.0"`, `collision_aabb_min_y="-6"`, `collision_aabb_max_y="3"`, `mass="1.3"` - Defines its collision bounds and mass.

## Material and Inventory

### Material Inventory Component (`MaterialInventoryComponent`)

Manages the materials the entity possesses and how they are handled.

| Attribute                 | Value | Description                                                              |
| :------------------------ | :---- | :----------------------------------------------------------------------- |
| `_enabled`                | `1`   | Enables the component.                                                   |
| `drop_as_item`            | `0`   | Does not drop its materials as a single item when defeated.              |
| `leak_on_damage_percent`  | `0.999` | Leaks almost all its material when damaged significantly.                |

#### Material Counts

| Material    | Count | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `blood_fungi` | `400` | Contains 400 units of `blood_fungi`.      |

## Scripting Components (`LuaComponent`)

These components execute custom Lua scripts for various functionalities.

| Script File                                     | Execution Trigger                  | Notes                                                              |
| :---------------------------------------------- | :--------------------------------- | :----------------------------------------------------------------- |
| `data/scripts/animals/fungus_death.lua`         | `script_death`                     | Executed when the entity dies.                                     |
| `data/scripts/perks/fungus_init.lua`            | `script_source_file`, `execute_on_added="1"`, `remove_after_executed="1"` | Initializes perk-related logic upon entity creation and is removed after. |
| `data/scripts/animals/fungus_death.lua`         | `script_collision_trigger_timer_finished`, `remove_after_executed="1"` | Triggered when a collision timer finishes.                         |
| `data/scripts/animals/fungus_smoke.lua`         | `script_collision_trigger_hit`, `remove_after_executed="1"` | Triggered on collision, likely for visual effects.                 |

## Collision Triggers (`CollisionTriggerComponent`)

These components detect collisions and trigger events.

### Trigger 1

| Attribute              | Value | Description                                                              |
| :--------------------- | :---- | :----------------------------------------------------------------------- |
| `width`                | `10`  | Width of the trigger area.                                               |
| `height`               | `10`  | Height of the trigger area.                                              |
| `radius`               | `5`   | Radius of the trigger area.                                              |
| `required_tag`         | `enemy` | Only triggers if the colliding entity has the "enemy" tag.               |
| `timer_for_destruction`| `20`  | The trigger will self-destruct after 20 frames.                          |

### Trigger 2

| Attribute                     | Value | Description                                                              |
| :---------------------------- | :---- | :----------------------------------------------------------------------- |
| `width`                       | `10`  | Width of the trigger area.                                               |
| `height`                      | `10`  | Height of the trigger area.                                              |
| `radius`                      | `5`   | Radius of the trigger area.                                              |
| `required_tag`                | `enemy` | Only triggers if the colliding entity has the "enemy" tag.               |
| `timer_for_destruction`       | `0`   | The trigger does not self-destruct based on a timer.                     |
| `destroy_this_entity_when_triggered` | `0`   | Does not destroy the entity when triggered.                              |
| `remove_component_when_triggered` | `1`   | This specific collision trigger component is removed when it's triggered. |

## Particle Emitter (`ParticleEmitterComponent`)

Responsible for generating visual particle effects.

| Attribute                 | Value | Description                                                              |
| :------------------------ | :---- | :----------------------------------------------------------------------- |
| `emitted_material_name`   | `acid_gas` | The material of the particles to be emitted.                             |
| `offset.x`, `offset.y`    | `0`   | Emission origin relative to the entity's center.                         |
| `x_pos_offset_min/max`    | `-2` to `2` | Horizontal spread of emission.                                           |
| `y_pos_offset_min/max`    | `-2` to `2` | Vertical spread of emission.                                             |
| `x_vel_min/max`           | `-10` to `10` | Horizontal velocity range of emitted particles.                          |
| `y_vel_min/max`           | `-10` to `10` | Vertical velocity range of emitted particles.                            |
| `count_min/max`           | `1` to `2` | Number of particles emitted per burst.                                   |
| `lifetime_min/max`        | `0.6` to `1.8` | Duration in seconds each particle exists.                                |
| `create_real_particles`   | `1`   | Emits actual game particles.                                             |
| `emit_cosmetic_particles` | `0`   | Does not emit purely cosmetic particles.                                 |
| `emission_interval_min/max_frames` | `10` to `35` | The time in frames between particle emission bursts.                     |
| `is_emitting`             | `1`   | The emitter is active.                                                   |

## Audio Component (`AudioComponent`)

Manages sound effects for the entity.

| Attribute    | Value                      | Description                               |
| :----------- | :------------------------- | :---------------------------------------- |
| `file`       | `data/audio/Desktop/animals.bank` | The audio bank file.                      |
| `event_root` | `animals/fungus`           | The root event name for its sounds.       |

## Variable Storage (`VariableStorageComponent`)

Used to store custom variables or tags.

| Attribute | Value        | Description                               |
| :-------- | :----------- | :---------------------------------------- |
| `_tags`   | `no_gold_drop` | This entity will not drop gold.           |