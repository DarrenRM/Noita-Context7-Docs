---
title: Dark Ghost Crystal Entity
category: entities
---

# Dark Ghost Crystal Entity

This document describes the `darkghost_crystal.xml` entity, which represents a Dark Ghost Crystal in Noita. This entity is a building with specific damage, genome, hitbox, pathfinding, physics, and lighting properties, and is controlled by Lua scripts.

## Key Components and Attributes

### DamageModelComponent

This component defines the entity's health, how it takes damage, and its resistance to various damage types.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `hp`                      | Current health points of the entity.                                        |
| `max_hp`                  | Maximum health points the entity can have.                                  |
| `falling_damage_damage_max` | Maximum damage taken from falling.                                          |
| `falling_damage_height_min` | Minimum height required to start taking falling damage.                     |
| `fire_damage_amount`      | Amount of damage taken from fire per tick.                                  |
| `fire_probability_of_ignition` | Probability of igniting when exposed to fire.                               |
| `blood_material`          | Material that is spawned when the entity takes damage (e.g., `sand_blue`). |
| `ragdoll_material`        | Material used for the ragdoll when the entity dies (e.g., `ice_b2`).      |

### GenomeDataComponent

This component defines the entity's place in the game's ecosystem and its behavioral tendencies.

| Attribute        | Description                                     |
| :--------------- | :---------------------------------------------- |
| `food_chain_rank`| A numerical value representing its position in the food chain. |
| `herd_id`        | Identifier for the entity's herd or group.      |
| `is_predator`    | Indicates if the entity is a predator (`1` for true, `0` for false). |

### HitboxComponent

This component defines the physical boundaries of the entity for collision detection.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `aabb_max_x`| Maximum X-coordinate of the bounding box.                                |
| `aabb_max_y`| Maximum Y-coordinate of the bounding box.                                |
| `aabb_min_x`| Minimum X-coordinate of the bounding box.                                |
| `aabb_min_y`| Minimum Y-coordinate of the bounding box.                                |
| `is_enemy`  | Whether this entity is considered an enemy (`1` or `0`).                 |
| `is_item`   | Whether this entity is considered an item (`1` or `0`).                  |
| `is_player` | Whether this entity is considered the player (`1` or `0`).               |

### PathFindingGridMarkerComponent

This component helps the entity interact with the pathfinding system.

| Attribute      | Description                                                              |
| :------------- | :----------------------------------------------------------------------- |
| `marker_work_flag` | A flag indicating the type of work this entity performs for pathfinding. |

### VelocityComponent

This component enables the entity to have velocity and move.

### SimplePhysicsComponent

This component enables basic physics interactions for the entity.

### LightComponent

This component defines the light emitted by the entity.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `radius`      | The radius of the light's influence.                                     |
| `fade_out_time`| How long it takes for the light to fade out.                             |
| `r`, `g`, `b` | Red, Green, and Blue color values for the light (0-255).               |
| `offset_y`    | Vertical offset of the light source from the entity's center.            |

### LuaComponent

These components execute Lua scripts associated with the entity.

| Attribute             | Description                                                                                             |
| :-------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_source_file`  | Path to the primary Lua script file executed when the entity is added.                                  |
| `script_death`        | Path to the Lua script file executed when the entity dies.                                              |
| `execute_on_added`    | If `1`, the `script_source_file` is executed immediately when the entity is added to the game world.    |
| `remove_after_executed`| If `1`, the Lua component is removed after its script has executed.                                     |
| `execute_every_n_frame`| If set to a positive integer, the script will execute every `n` frames. `-1` means execute once. |

---