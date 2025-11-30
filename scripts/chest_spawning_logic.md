---
title: Chest Spawning Logic
category: scripts
---

# Chest Spawning Logic

This script defines the logic for spawning random chests in Noita. It determines the number and type of chests to spawn at a given location.

## Core Functionality

The script's primary function is to randomly spawn chests when triggered.

### Key Attributes

*   **`count`**: Determines the number of chests to spawn. This is randomly set between 1 and 3.
*   **`types`**: A table containing the possible chest entity names that can be spawned. Currently includes:
    *   `"worm"`
    *   `"worm_big"`
    *   `"worm_tiny"`
*   **`EntityLoad`**: The function used to instantiate a chest entity.
    *   The specific entity loaded is `"data/entities/items/pickup/chest_random.xml"`.
    *   Chests are spawned with a random horizontal offset (`Random(-360, 360)`) from the script's origin and a fixed vertical offset (`-300`).
*   **`GameScreenshake`**: Triggers a screen shake effect (magnitude 30) after chests are spawned.

## Script Breakdown

1.  **Initialization**:
    *   Includes utility functions.
    *   Retrieves the current entity's ID and position.
    *   Sets a random seed based on game frame and entity position for deterministic randomness.

2.  **Chest Selection**:
    *   A random `count` (1-3) is determined.
    *   A list of possible `types` of chests is defined.

3.  **Spawning Loop**:
    *   The script iterates `count` times.
    *   In each iteration, a random `entity` type is selected from the `types` table.
    *   If a valid entity type is selected, `EntityLoad` is called to spawn a `chest_random.xml` entity at a randomized position.

4.  **Visual Feedback**:
    *   A screen shake is applied to indicate the spawning event.