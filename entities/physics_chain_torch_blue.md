---
title: Physics Chain Torch (Blue)
category: entities
---

# Physics Chain Torch (Blue)

This entity represents a blue, physics-enabled torch that hangs and emits light and particles. It's designed to be part of a chain or similar physics-driven structure.

## Key Components

### PhysicsBodyComponent
Manages the physical properties of the torch.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `allow_sleep`       | Allows the body to go to sleep when not in motion.                       |
| `angular_damping`   | Resistance to rotational movement.                                       |
| `fixed_rotation`    | Prevents the body from rotating.                                         |
| `is_bullet`         | Indicates if the body is a bullet (not applicable here).                |
| `linear_damping`    | Resistance to linear movement.                                           |
| `auto_clean`        | Automatically removes the physics body when it's no longer needed.       |
| `update_entity_transform` | Updates the entity's transform based on physics simulation.          |
| `on_death_leave_physics_body` | The physics body persists even if the entity is destroyed.           |

### PhysicsImageShapeComponent
Defines the visual shape of the physics body using an image.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `body_id`     | Links this shape to a specific `PhysicsBodyComponent`.                   |
| `centered`    | Centers the image on the physics body's origin.                          |
| `image_file`  | Path to the image file used for the shape.                               |
| `material`    | The material properties of the shape (e.g., `metal_nohit` means it can't be hit). |

### LuaComponent (Primary Script)
Executes a Lua script for the torch's behavior.

| Attribute              | Description                                                              |
| :--------------------- | :----------------------------------------------------------------------- |
| `execute_every_n_frame`| How often the script is executed (every frame in this case).             |
| `remove_after_executed`| Removes the component after the script has run once.                     |
| `script_source_file`   | Path to the main Lua script file controlling the torch's logic.          |

### LuaComponent (Damage Script)
Handles specific physics modifications when the torch is damaged.

| Attribute                     | Description                                                              |
| :---------------------------- | :----------------------------------------------------------------------- |
| `_enabled`                    | Whether this component is active.                                        |
| `script_physics_body_modified`| Path to the Lua script executed when the physics body is modified.       |

### InheritTransformComponent
Allows the entity to inherit transformations from its parent.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `position.x`| X-coordinate offset.                                                     |
| `position.y`| Y-coordinate offset.                                                     |

### LightComponent
Defines the light emitted by the torch.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `_tags`         | Tags that enable this component under certain conditions.                |
| `radius`        | The radius of the light's illumination.                                  |
| `fade_out_time` | How long it takes for the light to fade out.                             |

### TorchComponent
Specific component for torch functionality.

| Attribute             | Description                                                              |
| :-------------------- | :----------------------------------------------------------------------- |
| `_tags`               | Tags that enable this component under certain conditions.                |
| `fire_audio_weight`   | Controls the intensity of fire-related audio.                            |
| `suffocation_check_offset_y` | Offset for checking suffocation conditions.                          |

### SpriteAnimatorComponent
Handles sprite animations for the torch.

### Base (Particle Emitters)
This section inherits from `base_torch_particle.xml` and defines particle effects.

#### ParticleEmitterComponent (Multiple Instances)
These components define the emission of particles.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `x_pos_offset_min/max`  | Minimum and maximum X-axis offset for particle emission.                 |
| `y_pos_offset_min/max`  | Minimum and maximum Y-axis offset for particle emission.                 |
| `color`                 | The color of the emitted particles (hexadecimal format).                 |
| `emitted_material_name` | The name of the material to be emitted as particles (e.g., `spark_blue`).|

### CameraBoundComponent
Manages how the entity interacts with the camera's view.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `max_count` | Maximum number of these entities that can be active within the camera's view. |
| `distance`  | The maximum distance from the camera at which the entity is considered.  |