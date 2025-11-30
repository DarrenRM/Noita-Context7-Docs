---
title: Physics Torch Stand
category: entities
---

# Physics Torch Stand

This document describes the `physics_torch_stand_intro.xml` entity, which represents a basic torch stand in Noita. It's a prop with physics properties, a light source, and particle effects to simulate fire.

## Key Components

### PhysicsBodyComponent
This component defines the physical behavior of the torch stand.

*   **`uid`**: Unique identifier for the component.
*   **`allow_sleep`**: `1` - Allows the physics body to go to sleep when inactive to save performance.
*   **`angular_damping`**: `0.1` - Resistance to rotational movement.
*   **`fixed_rotation`**: `0` - Allows the torch stand to rotate.
*   **`is_bullet`**: `0` - Not a projectile.
*   **`auto_clean`**: `0` - The entity will not be automatically removed.
*   **`update_entity_transform`**: `1` - The entity's transform will be updated based on physics.
*   **`on_death_leave_physics_body`**: `1` - The physics body remains even if the entity is destroyed.

### PhysicsImageShapeComponent
Defines the physical shape of the entity using an image.

*   **`body_id`**: `1` - Links this shape to the `PhysicsBodyComponent` with `uid="1"`.
*   **`centered`**: `1` - The image is centered on the entity's origin.
*   **`image_file`**: `data/props_gfx/torch_stand_base.png` - The sprite used for the physical shape.
*   **`material`**: `metal_nohit` - The material properties for physics interactions.

### DamageModelComponent
Handles damage and health for the torch stand.

*   **`hp`**: `0.3` - Very low health, easily destroyed.
*   **`air_needed`**: `0` - Does not require air.
*   **`blood_material`**: `fire` - When damaged, it can interact with fire.
*   **`falling_damage_damage_max`**: `1.2` - Maximum damage from falling.
*   **`falling_damage_damage_min`**: `0.1` - Minimum damage from falling.
*   **`falling_damage_height_max`**: `250` - Maximum height for falling damage to apply.
*   **`falling_damage_height_min`**: `70` - Minimum height for falling damage to apply.
*   **`falling_damages`**: `1` - The entity can take falling damage.
*   **`fire_damage_amount`**: `0.2` - Amount of damage taken from fire.
*   **`fire_probability_of_ignition`**: `0` - Cannot ignite from fire.
*   **`materials_damage`**: `1` - Can be damaged by materials.
*   **`ragdoll_material`**: `wood_prop` - Material for ragdoll physics if it were to break apart.

### Inherited Entity (Base Torch Particle)
This section defines the visual and functional aspects of the torch itself, often inherited from a base entity.

#### LightComponent
Provides the light emitted by the torch.

*   **`_tags`**: `enabled_in_world,enabled_in_hand,fire` - Controls when the light is active.
*   **`radius`**: `166` - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.

#### TorchComponent
Specific component for torch functionality.

*   **`_tags`**: `enabled_in_world,enabled_in_hand` - Controls when the torch is active.
*   **`fire_audio_weight`**: `0.35` - Influences the intensity of fire sounds.
*   **`suffocation_check_offset_y`**: `-3` - Offset for checking if the torch is suffocated by other entities.

#### SpriteAnimatorComponent
Handles sprite animations for the torch.

#### Base file: `data/entities/base_torch_particle.xml`
This indicates that the torch stand inherits particle emitter configurations from a base torch particle entity.

##### ParticleEmitterComponent (Multiple)
These components define the fire particles emanating from the torch.

*   **`x_pos_offset_min`**: `-3` - Minimum horizontal offset for particle emission.
*   **`x_pos_offset_max`**: `2` - Maximum horizontal offset for particle emission.

These multiple emitters likely contribute to a more dynamic and varied fire effect.