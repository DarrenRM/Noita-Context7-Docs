---
title: Electrocution Effect Entity
category: entities
---

# Electrocution Effect Entity

This entity defines the visual and functional aspects of the electrocution effect in Noita. It's primarily used to apply the "ELECTROCUTION" status effect to entities.

## Key Components

### Base Entity

*   **`SpriteParticleEmitterComponent`**: Controls the visual particles associated with the electrocution.
    *   `randomize_position_inside_hitbox`: When set to `1`, particles will spawn randomly within the entity's hitbox.

### Game Effect Component

*   **`GameEffectComponent`**: This is the core component that applies the electrocution effect.
    *   `effect`: Specifies the type of game effect to apply. Here, it's set to `"ELECTROCUTION"`.
    *   `frames`: The duration of the electrocution effect in game frames.
    *   `disable_movement`: If set to `1`, the affected entity's movement will be disabled during the effect.
    *   `ragdoll_effect`: Defines the type of ragdoll effect. `"CUSTOM_RAGDOLL_ENTITY"` indicates a custom ragdoll entity will be used.
    *   `ragdoll_effect_custom_entity_file`: Specifies the XML file for the custom ragdoll entity, in this case, `"data/entities/props/physics_ragdoll_part_electrified.xml"`.

### Audio Loop Component

*   **`AudioLoopComponent`**: Manages the looping sound effect for electrocution.
    *   `file`: The audio bank file containing the sound.
    *   `event_name`: The specific event name within the audio bank for the electrocution loop.
    *   `auto_play`: If set to `1`, the sound will automatically start playing when the entity is active.