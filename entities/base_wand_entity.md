---
title: Base Wand Entity
category: entities
---

# Base Wand Entity

This document describes the core `base_wand.xml` entity, which serves as the foundation for all wands in Noita. It defines the fundamental properties and behaviors associated with wands, including their visual representation, particle effects, and pickup mechanics.

## Key Components

### SpriteParticleEmitterComponent

This component controls the visual effects associated with the wand, specifically the particle stream that emanates from it when used.

*   **`sprite_file`**: Specifies the particle sprite to use (e.g., `data/particles/ray.xml`).
*   **`lifetime`**: The duration each particle lives (in seconds).
*   **`color.r`, `color.g`, `color.b`, `color.a`**: Initial color of the particles.
*   **`color_change.r`, `color_change.g`, `color_change.b`, `color_change.a`**: How the color changes over the particle's lifetime.
*   **`scale.x`, `scale.y`**: Initial scale of the particles.
*   **`scale_velocity.x`, `scale_velocity.y`**: How the scale changes over the particle's lifetime.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Controls the rate at which particles are emitted.
*   **`emissive`**: Whether particles emit light.
*   **`additive`**: Whether particles use additive blending.
*   **`count_min`, `count_max`**: The number of particles emitted per emission event.
*   **`use_velocity_as_rotation`**: If true, particle rotation is determined by their velocity.
*   **`randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`**: Randomizes the emission position within a given range.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y`**: Randomizes the initial velocity of particles.
*   **`velocity_always_away_from_center`**: If true, particles are emitted away from the emitter's center.

### ItemAlchemyComponent

This component is typically used for items that can be affected by alchemy or have specific interactions within the game world. The `_tags="enabled_in_world"` ensures this component is active when the wand is in the game world.

### AudioLoopComponent

These components define looping sound effects associated with the wand.

*   **`_tags`**: Determines when the sound plays (e.g., `enabled_in_world`, `enabled_in_hand`).
*   **`file`**: The audio bank file containing the sound event.
*   **`event_name`**: The specific sound event to play.
*   **`volume_autofade_speed`**: Controls how quickly the volume fades out.

This entity includes two `AudioLoopComponent` instances:
*   `sound_digger`: Likely for a digging-type wand sound.
*   `sound_spray`: Likely for a spraying-type wand sound.

### Base Component

*   **`Base file="data/entities/base_wand_pickup.xml"`**: This crucial line indicates that the `base_wand.xml` entity inherits properties and behaviors from `base_wand_pickup.xml`. This means that the core logic for how wands are picked up and handled by the player is defined in that separate file.

## Summary

The `base_wand.xml` entity is a foundational element for wands. It primarily defines the visual particle effects and sound loops associated with wand usage. Its interaction with `base_wand_pickup.xml` signifies that the actual pickup and inventory logic for wands is handled elsewhere, making this file focused on the in-world visual and auditory representation of a wand.