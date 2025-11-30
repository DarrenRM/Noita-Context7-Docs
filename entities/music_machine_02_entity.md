---
title: Music Machine 02 Entity
category: entities
---

# Music Machine 02 Entity

This document describes the `music_machine_02.lua` entity, a type of music machine in Noita.

## Core Functionality

The primary function of this entity is to play a specific sound effect when "kicked" or interacted with.

### `kick` Function

The `kick` function is the main logic for this entity. It's triggered when the entity is interacted with.

*   **Purpose:** To play a sound, enable visual effects, and potentially attract fish.
*   **Trigger:** Called when the entity is "kicked" (likely through player interaction or other game events).
*   **Logic:**
    *   Retrieves the entity's ID.
    *   Checks the `AudioComponent` for the latest sound source.
    *   If no previous sound source is active (`src == -1`):
        *   Plays the sound "02" using `GameEntityPlaySound`.
        *   Enables components tagged with "fx" for visual effects.
        *   Adds the "fish\_attractor" tag to the entity.
        *   Sets a global flag `musicmachine3` using `GameAddFlagRun`.

## Key Attributes/Elements

While the provided Lua script focuses on the behavior, a typical Noita entity definition would include components that define its appearance, physics, and interaction. Based on the `kick` function, we can infer the presence of:

*   **`AudioComponent`**: Essential for playing sounds. The `kick` function directly interacts with this component to play "02".
*   **Tags**:
    *   `fx`: Indicates visual effects associated with the machine.
    *   `fish_attractor`: Suggests an interaction with fish mechanics in the game.

**Note:** The full entity definition (including components like `SpriteComponent`, `PhysicsComponent`, etc.) is not present in the provided `kick` function. This documentation focuses solely on the behavior defined in the `kick` function.