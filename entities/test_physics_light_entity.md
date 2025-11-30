---
title: Test Physics Light Entity
category: entities
---

# Test Physics Light Entity

This entity is a simple test case for physics and light interactions in Noita. It's designed to demonstrate how physics bodies and light sources can be combined.

## Key Components

### PhysicsBodyComponent
This component defines the physical properties of the entity.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `uid`               | Unique identifier for the physics body.                                     |
| `allow_sleep`       | If `1`, the physics body can go to sleep when not in motion to save resources. |
| `angular_damping`   | Resistance to rotational motion.                                            |
| `fixed_rotation`    | If `1`, the entity's rotation is locked.                                    |
| `is_bullet`         | If `1`, the physics body behaves like a bullet (e.g., collision detection). |
| `linear_damping`    | Resistance to linear motion.                                                |
| `auto_clean`        | If `1`, the physics body is automatically removed when it's no longer needed. |
| `update_entity_transform` | If `1`, the entity's transform is updated based on physics simulation.      |
| `on_death_leave_physics_body` | If `1`, the physics body remains after the entity is destroyed.             |

### PhysicsImageShapeComponent
This component defines the visual shape of the physics body using an image.

| Attribute    | Description                                                                 |
| :----------- | :-------------------------------------------------------------------------- |
| `body_id`    | References the `uid` of the `PhysicsBodyComponent` it's attached to.         |
| `centered`   | If `1`, the image is centered on the physics body.                          |
| `image_file` | Path to the image file used for the shape.                                  |
| `material`   | The material type, affecting interactions with other physics objects.       |

### LuaComponent
This component allows custom Lua scripting to be attached to the entity.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `_enabled`             | If `1`, the Lua script is active.                                           |
| `execute_every_n_frame`| The script will execute every `n` frames.                                   |
| `remove_after_executed`| If `1`, the Lua component is removed after its script has executed once.    |
| `script_source_file`   | Path to the Lua script file to be executed.                                 |

## Associated Lua Script

The `LuaComponent` points to `data/scripts/props/_test_physics_light.lua`. This script is responsible for the entity's behavior, likely involving light emission or interaction with the physics simulation. The specific functionality depends on the contents of that Lua file.