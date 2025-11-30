---
title: Altar Collapse Effect
category: scripts
---

# Altar Collapse Effect

This script defines the visual and auditory effects that occur when an altar collapses in Noita. It's designed to be triggered by game events and creates a dramatic visual spectacle.

## Core Functionality

The script utilizes asynchronous execution to manage timed events and visual effects.

### Key Attributes/Elements:

*   **`async(function () ... end)`**: This is the main wrapper for the script's logic, allowing for timed operations without blocking the game.
*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier of the entity that triggered this script.
*   **`EntityGetTransform(entity_id)`**: Gets the position (x, y coordinates) of the triggering entity.
*   **`GameScreenshake(intensity)`**: Triggers a screen shake effect. The `intensity` parameter controls the magnitude of the shake.
*   **`EntityLoad(entity_path, pos_x, pos_y)`**: Loads a specified entity from its XML file at the given coordinates.
    *   **`data/entities/particles/image_emitters/magical_symbol.xml`**: This entity is loaded to create a "magical symbol" particle effect.
    *   **`data/entities/misc/loose_chunks.xml`**: This entity is loaded to create a "loose chunks" effect, simulating debris.
*   **`wait(frames)`**: Pauses the execution of the script for a specified number of game frames. This is crucial for timing the sequence of effects.

## Execution Flow

1.  The script begins by getting the ID and position of the entity that initiated the collapse.
2.  A screen shake is immediately triggered with an intensity of 40.
3.  A "magical symbol" particle effect is spawned slightly above the entity's position.
4.  The script waits for 60 frames.
5.  After the wait, another screen shake of intensity 40 occurs.
6.  Finally, "loose chunks" are spawned slightly above the entity's position, simulating the altar breaking apart.

## Dependencies

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/lib/coroutines.lua`

These libraries are assumed to provide essential utility functions for asynchronous operations and general game scripting.