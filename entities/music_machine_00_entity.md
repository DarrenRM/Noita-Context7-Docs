---
title: Music Machine 00 Entity
category: entities
---

# Music Machine 00 Entity

This document describes the `music_machine_00.lua` entity, a basic music machine prop in Noita.

## Entity Definition

The entity is defined by the `kick` function, which is triggered when the machine is "kicked" or interacted with.

### `kick(who_kicked)` Function

This function handles the behavior of the music machine when activated.

*   **`entity = GetUpdatedEntityID()`**: Retrieves the ID of the entity that triggered the `kick` function.
*   **Audio Component Handling**:
    *   It attempts to get the `m_latest_source` from the `AudioComponent`.
    *   If `src == -1` (meaning no previous sound source is active), the following actions occur:
        *   **`GameEntityPlaySound( entity, "00" )`**: Plays the sound effect associated with this music machine (likely "00" from its name).
        *   **`EntitySetComponentsWithTagEnabled( entity, "fx", true )`**: Enables components tagged with "fx" on the entity, likely for visual effects.
        *   **`EntityAddTag( entity, "fish_attractor" )`**: Adds the "fish\_attractor" tag to the entity. This might influence fish behavior in the vicinity.
        *   **`GameAddFlagRun( "musicmachine1" )`**: Adds a game flag named "musicmachine1". This could be used to track the activation of this specific music machine or a group of them.

## Key Attributes/Elements

*   **Sound Playback**: The primary function is to play a specific sound effect.
*   **Visual Effects**: Can trigger associated visual effects.
*   **Game State Modification**: Can add game flags, potentially affecting gameplay or triggering events.
*   **Interaction Trigger**: Activated by an external "kick" or interaction.
*   **Tagging**: Can apply tags like "fish\_attractor" to influence entity interactions.