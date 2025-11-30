---
title: Dark Ghost Crystal Spawner
category: scripts
---

# Dark Ghost Crystal Spawner

This script defines the behavior for spawning a "Dark Ghost" entity when a specific building (presumably a crystal) is activated or interacted with.

## Core Functionality

The primary function `spawn_ghost()` is responsible for the entire spawning process.

### Key Actions:

1.  **Get Entity ID and Position:** Retrieves the unique identifier and world coordinates of the entity that triggered this script.
2.  **Load Dark Ghost Entity:** Instantiates a `darkghost.xml` entity at the current position. This is the actual "Dark Ghost" creature.
3.  **Configure Ghost Component:** Modifies the `GhostComponent` of the newly spawned Dark Ghost.
    *   **`mEntityHome`:** Sets the `mEntityHome` property of the ghost to the ID of the entity that spawned it. This likely establishes a connection or ownership.

## Script Structure

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions, though none are explicitly used in the provided snippet.
*   **`spawn_ghost()` function**: Encapsulates the spawning logic.
*   **`spawn_ghost()` call**: Executes the spawning function immediately when the script is loaded.

## Dependencies

*   `data/entities/animals/darkghost.xml`: The entity definition for the Dark Ghost.
*   `data/scripts/lib/utilities.lua`: A utility script (though its functions are not directly called here).

## AI Modding Considerations

*   **Triggering Mechanism:** The script itself doesn't define *how* `spawn_ghost()` is called. This is likely handled by the entity that *contains* this script (e.g., a building with a `GameEffectComponent` or similar that executes scripts).
*   **Ghost Behavior:** The behavior of the spawned Dark Ghost is defined within `darkghost.xml` and its associated scripts. This script only handles its initial placement and a basic home reference.
*   **Customization:** To alter the spawning behavior, one would typically modify:
    *   The entity that *uses* this script to change the trigger conditions.
    *   The `darkghost.xml` to change the ghost's appearance, AI, or abilities.
    *   This script itself to alter the spawning position or add further initial configurations to the ghost.