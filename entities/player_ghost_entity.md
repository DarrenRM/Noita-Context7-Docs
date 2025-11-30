---
title: Player Ghost Entity
category: entities
---

# Player Ghost Entity

This documentation describes the `playerghost.xml` entity, which represents the spawned ghost that carries an old wand in Noita. It is distinct from the `playerghost.xml` used as a polymorph target.

## Key Components and Attributes

### Base Entity

*   **`Base file="data/entities/base_apparition.xml"`**: Inherits core properties from the `base_apparition` entity.

### Camera Bound Component

*   **`CameraBoundComponent`**:
    *   `_enabled="0"`: This component is disabled by default.
    *   `max_count="30"`: Limits the maximum number of these entities that can be active.
    *   `distance="160000"`: Defines the distance from the camera within which the entity is considered.

### Music Energy Affector Component

*   **`MusicEnergyAffectorComponent`**:
    *   `energy_target="0.5"`: Influences the music energy, targeting a value of 0.5.

### Audio Loop Component

*   **`AudioLoopComponent`**:
    *   `file="data/audio/Desktop/animals.bank"`: Specifies the audio bank file.
    *   `event_name="animals/ghost/movement_loop"`: Sets the audio event for the ghost's movement loop.
    *   `set_speed_parameter="1"`: Enables setting a speed parameter for the audio.
    *   `auto_play="1"`: The audio loop starts automatically.

### Child Entity (Game Effect)

*   **`Entity`**: Contains a child entity with specific effects.
    *   **`InheritTransformComponent`**: Inherits transformation properties.
    *   **`GameEffectComponent`**:
        *   `effect="PROTECTION_FREEZE"`: Applies a freeze protection effect.
        *   `frames="-1"`: The effect lasts indefinitely.