---
title: Boss Centipede Pre-Fight Behavior
category: entities
---

# Boss Centipede Pre-Fight Behavior

This document details the AI behavior of the Boss Centipede entity before engaging in combat. It focuses on its movement patterns, limb animation, and audio cues.

## Core Functionality

The script controls the pre-fight animation and audio of the Boss Centipede. It dynamically adjusts limb positions and plays sounds based on player proximity.

### Key Attributes and Behaviors

*   **Limb Animation:** The script manages the movement of the centipede's limbs.
    *   **`limb_positions` Table:** Stores the current and target positions for each limb.
    *   **Random Animation:** Limbs animate randomly when the player is not nearby.
    *   **Player Proximity Animation:** When the player is close, limbs move in a more coordinated, circular pattern.
    *   **Interpolation:** Smoothly interpolates limb positions towards their target locations.
*   **Player Proximity Detection:**
    *   Detects the nearest player unit.
    *   Calculates the distance to the player.
    *   Sets a `player_nearby` flag if the player is within a certain range (128 units).
*   **Audio Cues:**
    *   Plays distinct sounds when the player enters or leaves the proximity range.
    *   Loops a "tinkering" sound when the player is not nearby.

### Script Logic Breakdown

The `async_loop` function orchestrates the entity's behavior:

1.  **Initialization:**
    *   Loads necessary utility scripts (`coroutines.lua`, `utilities.lua`).
    *   Initializes `limb_positions` table and `player_nearby_prev` flag.
2.  **Main Loop (`async_loop`):**
    *   **Get Entity and Player Data:** Retrieves the current entity's transform and checks for nearby players.
    *   **Limb Processing:** Iterates through each child entity (limb):
        *   Initializes limb position if not already set.
        *   Disables `IKLimbWalkerComponent` for the limb.
        *   Determines target limb positions based on player proximity or random chance.
        *   Calculates interpolated positions for smooth movement.
        *   Updates the `end_position` of the `IKLimbComponent`.
    *   **Audio Management:**
        *   Plays transition sounds based on changes in `player_nearby` status.
        *   Starts or stops the looping "tinkering" sound.
    *   **State Update:** Updates `player_nearby_prev` for the next iteration.
    *   **Wait:** Pauses for one frame (`wait(0)`) before the next loop iteration.

### Key Components and Functions Used

*   `dofile_once()`: Loads Lua files.
*   `async_loop()`: Creates an asynchronous loop for continuous updates.
*   `GetUpdatedEntityID()`: Gets the ID of the entity being updated.
*   `EntityGetTransform()`: Retrieves the position of an entity.
*   `EntityGetWithTag()`: Finds entities with a specific tag.
*   `EntityGetAllChildren()`: Gets all child entities of a given entity.
*   `edit_component()`: Modifies a component of an entity.
*   `EntitySetComponentIsEnabled()`: Enables or disables a component.
*   `ComponentGetValueVector2()`: Retrieves a 2D vector value from a component.
*   `ComponentSetValueVector2()`: Sets a 2D vector value for a component.
*   `GameEntityPlaySound()`: Plays a one-time sound effect.
*   `GameEntityPlaySoundLoop()`: Plays a looping sound effect.
*   `math.random()`: Generates random numbers.
*   `math.abs()`, `math.min()`, `math.max()`: Mathematical utility functions.
*   `math.cos()`, `math.sin()`: Trigonometric functions for circular movement.
*   `wait()`: Pauses execution within an async loop.