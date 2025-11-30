---
title: Wand Ghost Spawning Logic
category: scripts
---

# Wand Ghost Spawning Logic

This script defines the logic for spawning "wand ghosts," which are entities that appear to be animated wands. The primary function, `spawn_wand()`, controls when and how these entities are created.

## Key Functionality

### `spawn_wand()`

This function is responsible for the entire spawning process. It first checks the current number of existing "wand_ghost" entities in the game.

### Spawn Condition

*   **Maximum Wands:** The script prevents spawning new wand ghosts if there are already 4 or more entities with the tag "wand_ghost". This acts as a cap to prevent overwhelming the game.

### Spawning Mechanism

1.  **Entity ID and Position:** It retrieves the current entity's ID and its transform (position `x`, `y`).
2.  **Offset:** The spawn position is slightly offset from the current entity's position (`x = x + 50`).
3.  **Random Seed:** A random seed is generated using the current frame number and entity coordinates to ensure varied outcomes.
4.  **Entity Loading:** The "wand\_ghost.xml" entity is loaded at the calculated `x`, `y` position.
5.  **Velocity Component Modification:** The `edit_component` function is used to modify the `VelocityComponent` of the newly spawned wand ghost.
    *   **Random Velocity:** A random horizontal velocity (`vel_x`) between -90 and 90 is assigned.
    *   **Random Vertical Velocity:** A random vertical velocity (`vel_y`) between -150 and 25 is assigned. This gives the wand ghosts a somewhat erratic movement pattern.

## Core Components

*   **`EntityGetWithTag("wand_ghost")`**: Used to count existing entities with the specified tag.
*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity currently being processed.
*   **`EntityGetTransform(entity_id)`**: Gets the position of an entity.
*   **`SetRandomSeed(seed1, seed2)`**: Initializes the random number generator.
*   **`EntityLoad(xml_path, x, y)`**: Loads an entity from an XML file at a given position.
*   **`edit_component(entity_id, component_name, callback_function)`**: Allows modification of a specific component of an entity.
*   **`ComponentSetValueVector2(component, value_name, x, y)`**: Sets a 2D vector value for a component.

## Example Usage

The `spawn_wand()` function is called directly at the end of the script, meaning it will execute once when the script is loaded, attempting to spawn a wand ghost if the conditions are met.