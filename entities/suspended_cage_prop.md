---
title: Suspended Cage Prop
category: entities
---

# Suspended Cage Prop

This document describes the `suspended_cage.xml` entity, a prop used in Noita.

## Core Components

The suspended cage is defined by the following key components:

### `PhysicsBody2Component`

This component governs the physical behavior of the cage.

| Attribute        | Value   | Description                                      |
| :--------------- | :------ | :----------------------------------------------- |
| `is_static`      | `0`     | The cage is not static and can be moved.         |
| `allow_sleep`    | `1`     | The cage can enter a sleep state when idle.      |
| `angular_damping`| `0.01`  | Small value for gradual rotational slowdown.     |
| `linear_damping` | `0.3`   | Moderate value for gradual linear slowdown.      |
| `fixed_rotation` | `0`     | The cage's rotation is not fixed.                |
| `is_bullet`      | `0`     | The cage is not a projectile.                    |

### `PhysicsImageShapeComponent`

This component defines the visual representation and collision shape of the cage.

| Attribute   | Value                               | Description                                      |
| :---------- | :---------------------------------- | :----------------------------------------------- |
| `body_id`   | `100`                               | Unique identifier for the physics body.          |
| `is_root`   | `1`                                 | This is the root component for the physics shape.|
| `centered`  | `1`                                 | The image is centered on its origin.             |
| `image_file`| `data/props_gfx/suspended_cage.png` | Path to the sprite for the cage.                 |
| `material`  | `metal_prop`                        | The material type, affecting interactions.       |

### `LuaComponent`

This component enables custom scripting for the cage, specifically for chain generation.

| Attribute           | Value                                | Description                                      |
| :------------------ | :----------------------------------- | :----------------------------------------------- |
| `script_source_file`| `data/scripts/props/chain_to_ceiling.lua` | Path to the Lua script for chain behavior.       |
| `execute_on_added`  | `1`                                  | The script runs immediately when the entity is added.|
| `execute_every_n_frame`| `5`                                  | The script executes every 5 frames.              |
| `execute_times`     | `-1`                                 | The script executes indefinitely.                |

## Chain Generation Variables

The following `VariableStorageComponent`s are used by the `chain_to_ceiling.lua` script to define the chain's attachment points.

| Variable Name | Value Type | Value   | Description                                      |
| :------------ | :--------- | :------ | :----------------------------------------------- |
| `chain_0_x`   | `int`      | `-1`    | X-offset for the first chain segment.            |
| `chain_0_y`   | `int`      | `-5`    | Y-offset for the first chain segment.            |