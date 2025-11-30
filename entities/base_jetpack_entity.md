---
title: Base Jetpack Entity
category: entities
---

# Base Jetpack Entity

This document describes the `base_jetpack.xml` entity, which serves as a foundational component for jetpack functionality in Noita. It inherits from `base_jetpack_nosound.xml` and adds sound effects for jetpack operation.

## Key Components

### Base Entity Inheritance

*   **`Base file="data/entities/base_jetpack_nosound.xml"`**: This indicates that the jetpack entity inherits its core properties and behaviors from `base_jetpack_nosound.xml`. This is a common pattern in Noita for reusing and extending existing entity definitions.

### Audio Component

*   **`AudioLoopComponent`**: This component is responsible for playing a looping sound effect associated with the jetpack.
    *   **`_tags="sound_jetpack"`**: A tag used for identifying and potentially controlling this sound effect.
    *   **`file="data/audio/Desktop/animals.bank"`**: Specifies the audio bank file containing the sound event.
    *   **`event_name="animals/jetpack/movement_loop"`**: The specific name of the sound event to be triggered.
    *   **`volume_autofade_speed="0.25"`**: Controls how quickly the sound volume fades in or out.
    *   **`set_speed_parameter="1"`**: Likely links the sound's playback speed to a game parameter, such as the player's movement speed or jetpack thrust.