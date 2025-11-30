---
title: Workshop Collapse Script
category: scripts
---

# Workshop Collapse Script

This script defines the behavior for a workshop collapsing event in Noita. It triggers a series of visual and physical effects to simulate the destruction of a workshop.

## Key Functionality

The script utilizes asynchronous execution (`async`) to manage timed events and visual cues.

### Core Actions

*   **Screenshake:** Initiates screenshake effects at specific intervals to enhance the feeling of impact and destruction.
*   **Particle Emission:** Spawns a "magical\_symbol" particle effect at the workshop's location.
*   **Physics Removal:** Removes physics joints within a defined area around the workshop, simulating structural failure.
*   **Chunk Spawning:** Loads and spawns "loose\_chunks\_workshop" entities to represent debris.
*   **Player Debug Save:** Includes a function to save the player's state for debugging purposes.

### Script Flow

1.  **Initialization:**
    *   Loads utility and coroutine libraries.
    *   Starts an asynchronous function.
    *   Retrieves the entity ID and position of the workshop.

2.  **Initial Collapse:**
    *   Triggers a screenshake.
    *   Loads a magical symbol particle effect.
    *   Waits for 40 frames.

3.  **Structural Failure:**
    *   Triggers another screenshake.
    *   Removes physics joints in a specified area.
    *   Waits for 20 frames.

4.  **Debris Generation:**
    *   Triggers a final screenshake.
    *   Loads and spawns loose workshop chunks.
    *   Saves the player for debugging.

## Key Attributes/Elements

*   `entity_id`: The unique identifier for the workshop entity.
*   `pos_x`, `pos_y`: The X and Y coordinates of the workshop.
*   `GameScreenshake(intensity)`: Function to trigger screen shaking.
*   `EntityLoad(entity_path, x, y)`: Function to load and place an entity.
*   `wait(frames)`: Pauses script execution for a specified number of frames.
*   `PhysicsRemoveJoints(x1, y1, x2, y2)`: Removes physics joints within a bounding box.
*   `Debug_SaveTestPlayer()`: Saves the player's current state.

## Dependencies

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/lib/coroutines.lua`
*   `data/entities/particles/image_emitters/magical_symbol.xml`
*   `data/entities/misc/loose_chunks_workshop.xml`