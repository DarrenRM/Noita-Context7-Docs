---
title: Ghostly Chain Torch
category: entities
---

# Ghostly Chain Torch

This entity represents a ghostly, unlit torch that can be attached to a physics chain. It emits light and particles when active.

## Key Components

### PhysicsBodyComponent
Manages the physical properties of the torch.

*   `allow_sleep`: `1` - Allows the physics body to enter a sleep state when inactive.
*   `angular_damping`: `0.1` - Resistance to rotational movement.
*   `fixed_rotation`: `0` - Allows the torch to rotate freely.
*   `is_bullet`: `0` - Not a projectile.
*   `linear_damping`: `0` - No resistance to linear movement.
*   `auto_clean`: `0` - The entity is not automatically removed when it goes off-screen.
*   `update_entity_transform`: `1` - Updates the entity's transform based on physics.
*   `on_death_leave_physics_body`: `1` - Leaves a physics body behind upon death.

### PhysicsImageShapeComponent
Defines the visual shape and material of the torch for physics interactions.

*   `body_id`: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   `centered`: `1` - The image is centered on the physics body.
*   `image_file`: `data/props_gfx/torch_hang_unlit.png` - The sprite used for the unlit torch.
*   `material`: `metal_nohit` - The material type, which affects interactions.

### LuaComponent (Primary Script)
Executes the main logic for the torch.

*   `execute_every_n_frame`: `1` - Runs the script every frame.
*   `remove_after_executed`: `1` - The component is removed after its script finishes execution (likely on activation).
*   `script_source_file`: `data/scripts/props/physics_chain_torch.lua` - The primary Lua script controlling the torch's behavior.

### LuaComponent (Damage Script)
Handles behavior when the torch is damaged.

*   `_enabled`: `1` - This component is active.
*   `script_physics_body_modified`: `data/scripts/props/physics_chain_torch_damaged.lua` - The script to run when the physics body is modified (e.g., damaged).

### InheritTransformComponent
Allows inheriting transform properties from a parent entity.

*   `Transform`: Defines the relative position.
    *   `position.x`: `0`
    *   `position.y`: `0`

### LightComponent
Provides illumination.

*   `_tags`: `enabled_in_world,enabled_in_hand,fire` - Controls when the light is active.
*   `radius`: `96` - The range of the light.
*   `fade_out_time`: `1.5` - How long it takes for the light to fade out.

### TorchComponent
Specific component for torch functionality.

*   `_tags`: `enabled_in_world,enabled_in_hand` - Controls when the torch functionality is active.
*   `fire_audio_weight`: `0` - No significant impact on fire audio.
*   `suffocation_check_offset_y`: `-1` - Offset for suffocation checks.

### SpriteAnimatorComponent
Handles sprite animations. (No specific attributes shown, implies default behavior).

### Base (Particle Emitters)
Inherits from `base_torch_particle.xml` and adds specific particle emitters.

*   **ParticleEmitterComponent 1**:
    *   `x_pos_offset_min`: `-3`
    *   `x_pos_offset_max`: `2`
    *   `y_pos_offset_min`: `0`
    *   `y_pos_offset_max`: `2`
*   **ParticleEmitterComponent 2**:
    *   `color`: `ff50efe7` - A specific color for these particles.
    *   `emitted_material_name`: `spark_green` - The type of particle emitted.
    *   Offset values are the same as Component 1.
*   **ParticleEmitterComponent 3**:
    *   `emitted_material_name`: `spark_green` - The type of particle emitted.
    *   Offset values are the same as Component 1.

### CameraBoundComponent
Manages the entity's visibility and behavior relative to the camera.

*   `max_count`: `50` - Maximum number of these entities that can be active.
*   `distance`: `500` - The distance from the camera within which the entity is considered.