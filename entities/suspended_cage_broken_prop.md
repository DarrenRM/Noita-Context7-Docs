---
title: Suspended Cage (Broken) Prop
category: entities
---

# Suspended Cage (Broken) Prop

This document describes the `suspended_cage_broken.xml` entity, which represents a broken suspended cage prop in Noita.

## Key Components

### PhysicsBody2Component
This component defines the physical properties of the cage.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `is_static`      | `0`     | The object is not static and can be moved.      |
| `allow_sleep`    | `1`     | The object can enter a sleep state when idle.   |
| `angular_damping`| `0.01`  | Controls how quickly rotational velocity decays. |
| `linear_damping` | `0.3`   | Controls how quickly linear velocity decays.    |
| `fixed_rotation` | `0`     | The object's rotation is not fixed.             |
| `is_bullet`      | `0`     | This is not a projectile.                       |

### PhysicsImageShapeComponent
This component defines the visual representation and collision shape of the cage.

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `body_id`   | `100`                               | Identifier for the physics body.                |
| `is_root`   | `1`                                 | This is the root visual element.                |
| `centered`  | `1`                                 | The image is centered on its origin.            |
| `image_file`| `data/props_gfx/suspended_cage_broken.png` | Path to the sprite image.                       |
| `material`  | `metal_prop`                        | The material type, affecting interactions.      |

### LuaComponent
This component handles the logic for generating chains attached to the ceiling.

| Attribute           | Value                                | Description                                     |
| :------------------ | :----------------------------------- | :---------------------------------------------- |
| `script_source_file`| `data/scripts/props/chain_to_ceiling.lua` | The Lua script responsible for chain generation. |
| `execute_on_added`  | `1`                                  | The script runs when the entity is added.       |
| `execute_every_n_frame`| `5`                                  | The script executes every 5 frames.             |
| `execute_times`     | `-1`                                 | The script executes indefinitely.               |

### VariableStorageComponent
These components store integer variables used by the Lua script for chain positioning.

*   `chain_0_x`: Stores the X-offset for the first chain segment.
*   `chain_0_y`: Stores the Y-offset for the first chain segment.