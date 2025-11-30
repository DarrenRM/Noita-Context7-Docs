---
title: Fungus Powder Spawner
category: scripts
---

# Fungus Powder Spawner

This script is responsible for spawning "fungus" entities under specific conditions. It acts as a passive spawner, triggered by the presence of other entities.

## Core Functionality

The primary purpose of this script is to periodically spawn a "fungus" entity if certain criteria are met.

### Spawning Conditions

*   **Rats Count:** The script checks for entities with the tag "perk_fungus_tiny". If the count of these entities is less than 30, the spawning logic is considered.
*   **Random Chance:** A random chance of 1 in 20 (5 out of 20) determines if a new "fungus" entity will be spawned.

### Entity Spawning

*   **Entity Type:** The entity spawned is `data/entities/misc/perks/fungus.xml`.
*   **Position:** The spawned entity inherits the `x` and `y` coordinates of the entity running this script.
*   **Tag Removal:** The spawned "fungus" entity has its "enemy" tag removed.

### Script Execution

*   **Self-Destruction:** After its logic is executed, the entity running this script is immediately killed (`EntityKill(entity_id)`).
*   **Initialization:** The script uses `dofile_once` to ensure utility functions are loaded and `SetRandomSeed` to initialize the random number generator based on the entity's position.

## Key Attributes/Elements

*   `EntityLoad("data/entities/misc/perks/fungus.xml", x, y)`: The function used to spawn the "fungus" entity.
*   `EntityGetWithTag("perk_fungus_tiny")`: Retrieves all entities with the specified tag.
*   `EntityRemoveTag(eid, "enemy")`: Removes the "enemy" tag from the spawned entity.
*   `EntityKill(entity_id)`: Removes the entity running the script.
*   `Random(1, 20) == 5`: The core random chance check for spawning.