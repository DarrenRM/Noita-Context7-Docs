---
title: Music Machine Audio - Dead State
category: entities
---

# Music Machine Audio - Dead State

This document describes the Lua script for the "dead" state of a music machine entity in Noita, specifically focusing on its audio behavior.

## `audio_event_dead` Function

This function is triggered when the music machine enters its "dead" state.

### Key Actions:

*   **`EntitySetComponentsWithTagEnabled( entity, "fx", false )`**: Disables any components tagged with "fx" (likely visual effects or particle emitters) associated with the entity. This visually signifies the machine is no longer active.
*   **`EntityRemoveTag( entity, "fish_attractor" )`**: Removes the "fish\_attractor" tag from the entity. This suggests that when the music machine is dead, it no longer influences or attracts fish in the game world.

### Parameters:

*   **`file`**: The path to the script file.
*   **`event_root`**: The root entity ID for the event.

### Global Functions Used:

*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity that triggered this event.
*   **`EntitySetComponentsWithTagEnabled( entity, tag, enabled )`**: Enables or disables components of an entity based on a given tag.
*   **`EntityRemoveTag( entity, tag )`**: Removes a specific tag from an entity.