---
title: Music Machine 03 Entity
category: entities
---

# Music Machine 03 Entity

This document describes the `music_machine_03.lua` entity, a prop that plays music when interacted with.

## Core Functionality

The primary function of this entity is to play a specific sound effect when "kicked" or interacted with. It also triggers visual effects and adds a tag to the entity.

### `kick(who_kicked)` Function

This function is called when the entity is interacted with.

*   **`who_kicked`**: The entity that initiated the interaction.
*   **Sound Playback**:
    *   It checks if a sound is already playing from the `AudioComponent`.
    *   If no sound is playing (`src == -1`), it plays the sound associated with "03".
    *   It enables components with the tag "fx" for visual effects.
    *   It adds the "fish\_attractor" tag to the entity.
    *   It sets a game flag `musicmachine4`.

## Key Components and Attributes (Implied)

While the provided code snippet focuses on the `kick` function, the entity likely possesses the following components to enable its behavior:

### `AudioComponent`

*   **Purpose**: Handles sound playback.
*   **Key Attributes (Implied)**:
    *   `m_sound_event`: The name of the sound event to play (likely "03" based on the `kick` function).
    *   `m_latest_source`: Tracks the currently playing sound source.

### `SpriteComponent`

*   **Purpose**: Defines the visual appearance of the music machine.
*   **Key Attributes (Implied)**:
    *   `sprite`: The texture file for the music machine's sprite.
    *   `x`, `y`: Position of the sprite.
    *   `scale_x`, `scale_y`: Scaling of the sprite.

### `HitboxComponent`

*   **Purpose**: Defines the area that can be interacted with.
*   **Key Attributes (Implied)**:
    *   `x`, `y`, `w`, `h`: Dimensions and position of the hitbox.

### `TagComponent`

*   **Purpose**: Allows for tagging entities for various game logic.
*   **Key Attributes (Implied)**:
    *   `tags`: A list of tags associated with the entity (e.g., "fx", "fish\_attractor").

## Example Usage (Conceptual)

To use this entity in a Noita mod, you would typically define it in a `.lua` file within the `data/entities/props/music_machines/` directory. The `kick` function would be triggered by game mechanics that simulate an interaction, such as a player character colliding with or activating the entity.

```lua
-- Example of how this entity might be defined (simplified)
-- This is illustrative and not the full entity definition.

local entity = EntityLoad( "data/entities/props/music_machines/music_machine_03.lua" )

-- Further configuration or placement of the entity would occur here.
```