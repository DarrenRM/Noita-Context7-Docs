---
title: Physics Chain Torch
category: entities
---

# Physics Chain Torch

This entity defines a physics-based chain torch, composed of multiple segments connected by revolute joints. It's designed to hang from surfaces and emit light.

## Key Components

### PhysicsBody2Component
Manages the physical properties of the main body of the torch.

*   `allow_sleep`: `1` - Allows the physics body to go to sleep when inactive to save performance.
*   `angular_damping`: `0.01` - Controls how quickly rotational velocity decreases.
*   `linear_damping`: `0.1` - Controls how quickly linear velocity decreases.
*   `init_offset_x`: `1.5` - Initial offset for the physics body in the X direction.
*   `root_offset_x`: `4` - Offset for the root of the physics body in the X direction.
*   `root_offset_y`: `7` - Offset for the root of the physics body in the Y direction.

### PhysicsImageShapeComponent
Defines the visual representation and collision shape for each segment of the torch.

| Attribute    | Value                               | Description                                                              |
| :----------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `body_id`    | `0` to `4`                          | Identifies which physics body this shape is attached to.                 |
| `offset_x`   | `0` or `-3.5`                       | X-axis offset for the image shape.                                       |
| `offset_y`   | `0`, `6`, `12`, `18`, `24`          | Y-axis offset for the image shape, creating the chain effect.            |
| `image_file` | `data/props_gfx/...`                | Path to the sprite image for the segment.                                |
| `material`   | `metal_nohit`                       | The material properties of the shape, indicating it cannot be hit.       |
| `is_root`    | `1` (for `body_id="4"`)             | Marks this segment as the root of the chain, where the torch head is.    |

### PhysicsJoint2Component
Connects different physics bodies together, defining the type of joint and its properties.

| Attribute     | Value                               | Description                                                                                             |
| :------------ | :---------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `type`        | `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE` or `REVOLUTE_JOINT` | Defines the type of joint. The first joint attaches to the environment. |
| `break_force` | `8` or `4`                          | The force required to break the joint.                                                                  |
*   `offset_x`: `2` - X-axis offset for the joint.
*   `offset_y`: Varies - Y-axis offset for the joint, defining the connection point.
*   `body1_id`: `0` to `3` - The ID of the first physics body connected by the joint.
*   `body2_id`: `1` to `4` - The ID of the second physics body connected by the joint.

### LightComponent
Attached to the root entity, this component makes the torch emit light.

*   `radius`: `96` - The radius of the light emitted.
*   `fade_out_time`: `1.5` - How long it takes for the light to fade out.

### TorchComponent
Provides the functionality of a torch, including fire effects and audio.

*   `fire_audio_weight`: `0.5` - Controls the intensity of the fire sound.
*   `suffocation_check_offset_y`: `-1` - Offset for checking suffocation conditions related to the torch.

### ParticleEmitterComponent
(Inherited from `base_torch_particle.xml`)
Responsible for emitting particles that simulate fire and smoke.

*   `x_pos_offset_min`/`max`: `-3` to `2` - Range for X-axis particle emission position.
*   `y_pos_offset_min`/`max`: `0` to `2` - Range for Y-axis particle emission position.