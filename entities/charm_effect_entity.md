---
title: Charm Effect Entity
category: entities
---

# Charm Effect Entity

This entity defines the visual and auditory components of the "Charm" status effect in Noita. It's primarily used to create a visual indicator and sound cue when a character is charmed.

## Key Components

### Base Entity (`<Base file="data/entities/particles/charm.xml">`)

This tag inherits from a base particle entity, likely defining the fundamental visual properties of the charm effect.

### Sprite Particle Emitter (`<SpriteParticleEmitterComponent>`)

This component controls the emission of particles that form the visual representation of the charm effect.

*   **`emission_interval_min_frames`**: The minimum number of frames between particle emissions.
*   **`emission_interval_max_frames`**: The maximum number of frames between particle emissions.
*   **`randomize_position_inside_hitbox`**: If set to `1`, particles will be emitted at random positions within the entity's hitbox.

### Inherit Transform (`<InheritTransformComponent>`)

This component, when enabled (`_enabled="1"`), allows the charm effect to inherit the transform (position, rotation, scale) of its parent entity. This is crucial for the effect to appear attached to the charmed character or object.

### Game Effect (`<GameEffectComponent>`)

This component links the entity to a specific game effect.

*   **`effect`**: Set to `"CHARM"`, indicating this entity is associated with the charm status effect.
*   **`frames`**: Set to `"-1"`, suggesting the charm effect is intended to be persistent or last for an indefinite duration until removed by game logic.

### Audio Component (`<AudioComponent>`)

This component handles the sound associated with the charm effect.

*   **`file`**: Specifies the audio bank file: `"data/audio/Desktop/misc.bank"`.
*   **`event_root`**: Defines the root event name for the charm sound: `"game_effect/charm"`. This allows for specific charm-related sound events to be triggered from this bank.