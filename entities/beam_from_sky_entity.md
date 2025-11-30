---
title: Beam From Sky Entity
category: entities
---

# Beam From Sky Entity

This entity simulates a beam of energy descending from the sky, dealing damage and affecting the ground.

## Core Components

### LuaComponent
This component links the entity to its behavior script.

| Attribute           | Value                               | Description                                                                 |
| :------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/magic/beam_from_sky.lua` | The Lua script that defines the entity's logic and behavior.                |
| `vm_type`           | `ONE_PER_COMPONENT_INSTANCE`        | Specifies how the Lua virtual machine is managed.                           |
| `enable_coroutines` | `1`                                 | Enables the use of coroutines within the Lua script.                        |
| `execute_on_added`  | `1`                                 | The script will execute immediately when the entity is added to the world.  |
| `execute_times`     | `1`                                 | The script will execute only once.                                          |

### LifetimeComponent
Determines how long the entity persists in the game world.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `190` | The entity will exist for 190 frames.     |

### AreaDamageComponent
Handles the damage dealt by the entity in a specific area.

| Attribute        | Value             | Description                                                                                             |
| :--------------- | :---------------- | :------------------------------------------------------------------------------------------------------ |
| `_enabled`       | `0`               | This component is initially disabled.                                                                   |
| `_tags`          | `enabled_in_world`| This component is only active when the entity is in the game world.                                     |
| `aabb_min.x`     | `-40`             | Minimum X-coordinate of the damage area.                                                                |
| `aabb_min.y`     | `-10000`          | Minimum Y-coordinate of the damage area (effectively very far down).                                    |
| `aabb_max.x`     | `40`              | Maximum X-coordinate of the damage area.                                                                |
| `aabb_max.y`     | `5`               | Maximum Y-coordinate of the damage area.                                                                |
| `damage_per_frame`| `5`               | The amount of damage dealt per frame to entities within the area.                                       |
| `update_every_n_frame`| `1`               | The damage area is updated every frame.                                                                 |
| `entities_with_tag`| `mortal`          | Only entities with the tag "mortal" will be affected by the damage.                                     |
| `damage_type`    | `DAMAGE_PROJECTILE`| The type of damage dealt.                                                                               |
| `death_cause`    | `$damage_plasmabeam`| The string ID used to identify the cause of death for this damage type.                                 |

### LooseGroundComponent
This component causes the ground within the entity's influence to become loose or break apart.

| Attribute       | Value | Description                                                                                             |
| :-------------- | :---- | :------------------------------------------------------------------------------------------------------ |
| `probability`   | `0.2` | The probability that ground will be affected when the entity is active.                                 |
| `max_angle`     | `1.6` | The maximum angle at which ground can be affected.                                                      |
| `max_distance`  | `200` | The maximum distance from the entity that ground can be affected.                                       |

The second `LooseGroundComponent` is disabled by default and has a `probability` of `1.0`, suggesting it might be an alternative or more potent effect intended for specific scenarios.

## Visual Effects (Particle Emitters)

The entity utilizes multiple `ParticleEmitterComponent`s to create visual effects.

### Green Spark Emitter
This emitter generates green sparks.

| Attribute              | Value   | Description