---
title: Spore Pod Growing Perk
category: scripts
---

---

# Spore Pod Growing Perk

This script handles the functionality of the "Spore Pod Growing" perk in Noita. When a player picks up this perk, it triggers the spawning of a special projectile that, upon impact, creates a "Spore Pod" entity.

## Core Functionality

The primary action of this script is to initiate the spawning of a projectile. This projectile is designed to be a precursor to the Spore Pod entity itself.

### Key Actions

*   **`shoot_projectile_from_projectile`**: This is the core function called by the script. It spawns a new projectile entity.
    *   **`entity_id`**: The ID of the entity that is currently executing this script (likely the player or a related perk entity).
    *   **`"data/entities/misc/perks/spore_pod_growing.xml"`**: The XML file defining the properties and behavior of the projectile that will be spawned. This XML will contain the logic for what happens when the projectile hits something.
    *   **`x, y`**: The coordinates where the projectile will be spawned. These are derived from the current entity's position.
    *   **`0, 0`**: These likely represent the initial velocity components (x and y) of the spawned projectile. In this case, it's spawned with no initial movement.

## Initialization

The script begins with standard Noita initialization procedures.

### Setup

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Includes a utility library, likely containing helper functions for game development.
*   **`local entity_id = GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity.
*   **`local x, y = EntityGetTransform( entity_id )`**: Gets the current position (x, y coordinates) of the entity.
*   **`SetRandomSeed( x * entity_id, y + GameGetFrameNum() )`**: Sets a random seed based on the entity's position and the current game frame. This is crucial for ensuring that random events (like projectile behavior or subsequent entity spawning) are consistent for a given game state but vary between different playthroughs.