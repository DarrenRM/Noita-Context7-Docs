---
title: Hanging Wire Prop
category: entities
---

# Hanging Wire Prop

This document describes the `physics_hanging_wire.xml` entity, which represents a physics-driven hanging wire prop in Noita.

## Key Components

### PhysicsBody2Component

This component governs the physical behavior of the wire.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `allow_sleep`       | Whether the physics body can enter a sleeping state to save performance.    |
| `angular_damping`   | Resistance to rotational movement.                                          |
| `linear_damping`    | Resistance to linear movement.                                              |
| `kill_entity_after_initialized` | If true, the entity will be destroyed after its physics are initialized. |
| `manual_init`       | If true, physics initialization needs to be triggered manually.             |
| `init_offset_y`     | An initial vertical offset applied during physics initialization.           |
| `auto_clean`        | If true, the entity is automatically cleaned up when it goes off-screen.    |

### LuaComponent

This component attaches a Lua script to the entity, enabling custom behavior.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_source_file`| The path to the Lua script file to be executed.                             |
| `execute_on_added`  | If true, the script will execute immediately after the entity is added.     |
| `execute_every_n_frame` | The script will execute every N frames.                                     |
| `execute_times`     | The number of times the script should execute. `-1` means indefinitely.     |