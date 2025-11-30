---
title: Tiny Maggot Entity
category: entities
---

# Tiny Maggot Entity

This document details the configuration of the Tiny Maggot entity in Noita, focusing on its core attributes and behaviors relevant to modding.

## Core Entity Properties

The Tiny Maggot is an enemy entity with several inherent tags that define its basic interactions within the game world.

### Entity Tags

*   `enemy`: Identifies the entity as a hostile creature.
*   `hittable`: Allows the entity to be damaged by player attacks.
*   `teleportable_NOT`: Prevents the entity from being teleported.
*   `homing_target`: Indicates it can be targeted by homing projectiles.
*   `glue_NOT`: The entity is not affected by glue.
*   `necrobot_NOT`: The entity is not affected by Necrobot.
*   `polymorphable_NOT`: The entity cannot be polymorphed.
*   `touchmagic_immunity`: The entity is immune to touch-based magic effects.

## Key Components and Attributes

The following components define the Tiny Maggot's appearance, behavior, and combat capabilities.

### BossDragonComponent

This component governs the movement and AI of the Tiny Maggot, giving it dragon-like characteristics.

*   `speed`: Base movement speed.
*   `speed_hunt`: Movement speed when actively pursuing a target.
*   `acceleration`: How quickly the entity reaches its target speed.
*   `direction_adjust_speed`: How quickly the entity adjusts its direction.
*   `direction_adjust_speed_hunt`: Direction adjustment speed when hunting.
*   `tail_gravity`: Affects the behavior of its segmented body.
*   `part_distance`: The distance between segments of its body.
*   `hitbox_radius`: The radius of the entity's primary hitbox.
*   `hunt_box_radius`: The radius within which the entity will actively hunt targets.
*   `random_target_box_radius`: The radius within which the entity will seek random targets.
*   `new_hunt_target_check_every`: How often the entity checks for new hunt targets (in frames).
*   `new_random_target_check_every`: How often the entity checks for new random targets (in frames).

### DamageModelComponent

Defines the health, damage resistances, and visual effects associated with the Tiny Maggot taking damage.

*   `hp`: The entity's health points.
*   `fire_damage_amount`: Amount of fire damage it deals (set to 0).
*   `fire_how_much_fire_generates`: How much fire it generates when hit (set to 0).
*   `ragdoll_fx_forced`: The visual effect played when the entity is disintegrated.
*   `materials_damage`: Whether the entity damages materials it touches.
*   `blood_material`: The material used for blood effects.
*   `blood_spray_material`: The material used for blood spray effects.
*   `blood_multiplier`: Controls the intensity of blood effects.
*   `damage_multipliers`: Modifiers for damage taken from different sources.

#### Damage Multipliers

| Type       | Multiplier |
| :--------- | :--------- |
| `explosion`| `0.5`      |
| `fire`     | `0.5`      |
| `ice`      | `0.5`      |
| `electricity`| `0.3`      |
| `projectile`| `0.0`      |

### GenomeDataComponent

This component relates the Tiny Maggot to the game's ecosystem and genetic system.

*   `herd_id`: Identifies the genetic herd it belongs to.
*   `food_chain_rank`: Its position in the food chain.
*   `is_predator`: Indicates if it's a predator.

### SpriteComponent

Multiple `SpriteComponent` instances define the visual appearance of the Tiny Maggot, including its head, body segments, and tail.

*   `image_file`: Path to the sprite's image data.
*   `rect_animation`: The current animation state.
*   `next_rect_animation`: The animation to transition to.
*   `z_index`: Controls the rendering order of sprites.

Special `SpriteComponent`s are used for the health bar UI elements.

### LightComponent

*   `radius`: The radius of the light emitted.
*   `r`, `g`, `b`: The color components of the light.

### LuaComponent

Scripts are attached to control specific behaviors.

*   `script_death`: A Lua script executed when the entity dies.
*   `script_source_file`: Path to a Lua script for ongoing behavior.
*   `execute_every_n_frame`: How often the script's logic is executed.

### AudioLoopComponent

*   `file`: The audio bank file.
*   `event_name`: The specific sound event to play.
*   `set_speed_parameter`: Whether to link sound speed to entity movement.
*   `auto_play`: If the sound should start automatically.

### AreaDamageComponent

This component allows the Tiny Maggot to inflict damage on entities within a certain area.

*   `aabb_min.x`, `aabb_min.y`, `aabb_max.x`, `aabb_max.y`: Defines the bounding box for area damage.
*   `damage_per_frame`: The amount of damage dealt per frame.
*   `update_every_n_frame`: How often the damage is applied.
*   `entities_with_tag`: Which entities are affected by this area damage.
*   `damage_type`: The type of damage inflicted (e.g., `DAMAGE_CURSE`).

### Other Notable Components

*   `StreamingKeepAliveComponent`: Ensures the entity remains loaded.
*   `PathFindingGridMarkerComponent`: Helps the entity navigate the game world.
*   `CellEaterComponent`: Defines its ability to consume cells.
*   `BossHealthBarComponent`: Enables a boss health bar.
*   `MusicEnergyAffectorComponent`: Affects music energy.
*   `InheritTransformComponent`: Used in nested entities to inherit transformations.
*   `GameEffectComponent`: Applies status effects like stun protection.
*   `VariableStorageComponent`: Stores custom variables.

## Nested Entities

The Tiny Maggot utilizes nested `Entity` blocks to define additional visual elements and behaviors, such as emissive sprites and stain effects. These often inherit transformations from parent sprites and have their own `GenomeDataComponent` and `LuaComponent` configurations.

The emissive sprites contribute to the visual flair, while the `stain.lua` script likely handles the creation of visual "stains" or effects as the entity moves. The `execute_every_n_frame` values for these stain scripts vary, suggesting subtle differences in their application timing.

The entity also includes nested entities for `STUN_PROTECTION_FREEZE`, `STUN_PROTECTION_ELECTRICITY`, and `PROTECTION_PROJECTILE`, granting it resistances to these damage types.