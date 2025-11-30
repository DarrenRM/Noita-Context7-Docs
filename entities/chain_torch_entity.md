---
title: Chain Torch Entity
category: entities
---

# Chain Torch Entity

This document describes the `chain_torch.xml` entity, a common light source in Noita. It inherits functionality from base torch and particle entities to provide light and visual effects.

## Key Components

### Base Entity Inheritance

*   **`<Base file="data/entities/base_chain_torch.xml" />`**: This is the primary inheritance, providing core functionality for a chain torch.

### Transform Component

*   **`<InheritTransformComponent>`**: Manages the entity's position and orientation.
    *   **`<Transform position.x="0" position.y="0" />`**: Sets the default relative position of the torch.

### Light Component

*   **`<LightComponent _tags="fire" radius="96" fade_out_time="1.5" />`**: Defines the light emitted by the torch.
    *   `_tags="fire"`: Associates this light with fire effects.
    *   `radius="96"`: The maximum distance the light will reach.
    *   `fade_out_time="1.5"`: How long it takes for the light to fade out.

### Torch Component

*   **`<TorchComponent fire_audio_weight="0.5" suffocation_check_offset_y="-1" />`**: Specific properties for torch behavior.
    *   `fire_audio_weight="0.5"`: Influences the intensity of associated fire sounds.
    *   `suffocation_check_offset_y="-1"`: An offset used for checking suffocation conditions related to the torch.

### Sprite Animator Component

*   **`<SpriteAnimatorComponent />`**: Handles sprite animations for the torch.

### Particle Emitter Components (Inherited)

*   **`<Base file="data/entities/base_torch_particle.xml" >`**: Inherits particle effects from a base torch particle definition.
    *   **`<ParticleEmitterComponent x_pos_offset_min="-3" x_pos_offset_max="2" y_pos_offset_min="0" y_pos_offset_max="2" />`**: Multiple instances of this component define where and how particles are emitted around the torch, contributing to the visual "fire" effect.
        *   `x_pos_offset_min`, `x_pos_offset_max`: Defines the horizontal spread of particle emission.
        *   `y_pos_offset_min`, `y_pos_offset_max`: Defines the vertical spread of particle emission.