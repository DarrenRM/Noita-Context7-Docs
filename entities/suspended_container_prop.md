---
title: Suspended Container Prop
category: entities
---

# Suspended Container Prop

This entity represents a physics-enabled suspended container, typically used for decorative or interactive elements in the game world. It utilizes physics components for movement and collision, and Lua scripts for its behavior, including chain generation.

## Key Components

### `PhysicsBody2Component`

Manages the physical properties of the container.

| Attribute        | Description                                     |
| :--------------- | :---------------------------------------------- |
| `is_static`      | `0` - The body is dynamic and can move.         |
| `allow_sleep`    | `1` - The body can enter a sleep state when idle. |
| `angular_damping`| `0.01` - Resistance to rotational movement.     |
| `linear_damping` | `0.3` - Resistance to linear movement.          |
| `fixed_rotation` | `0` - The body can rotate freely.               |
| `is_bullet`      | `0` - Not treated as a projectile.              |

### `PhysicsImageShapeComponent`

Defines the visual representation and collision shape of the container.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `body_id`   | `100` - Identifier for the physics body.        |
| `is_root`   | `1` - This is the primary shape for the entity. |
| `centered`  | `1` - The image is centered on its origin.      |
| `image_file`| `data/props_gfx/suspended_container.png` - Path to the sprite. |
| `material`  | `metal_prop` - The material type for physics interactions. |

### `LuaComponent` (Physics Objects)

Executes a Lua script to manage the physics behavior of the container.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/props/suspended_container_physics_objects.lua` - The script file. |
| `execute_every_n_frame` | `1` - Script logic runs every frame.                                     |
| `execute_times`     | `1` - Script logic executes only once.                                   |

### `LuaComponent` (Chain Generation)

Executes a Lua script to generate chains attached to the ceiling.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/props/chain_to_ceiling.lua` - The script file.             |
| `execute_on_added`  | `1` - Script logic runs when the entity is added to the game world.      |
| `execute_every_n_frame` | `5` - Script logic runs every 5 frames.                                  |
| `execute_times`     | `-1` - Script logic executes indefinitely.                               |

## Chain Generation Variables

These `VariableStorageComponent` entries define the relative positions for chain attachment points.

| Name        | Value Type | Value | Description                               |
| :---------- | :--------- | :---- | :---------------------------------------- |
| `chain_0_x` | `int`      | `-16` | X-offset for the first chain attachment.  |
| `chain_0_y` | `int`      | `-8`  | Y-offset for the first chain attachment.  |
| `chain_1_x` | `int`      | `13`  | X-offset for the second chain attachment. |
| `chain_1_y` | `int`      | `-8`  | Y-offset for the second chain attachment. |