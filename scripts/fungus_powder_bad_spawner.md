---
title: Fungus Powder Bad Spawner
category: scripts
---

# Fungus Powder Bad Spawner

This script controls the spawning behavior of "fungus_tiny_bad" entities. It acts as a spawner that periodically creates these entities if their current count is below a certain threshold.

## Core Functionality

*   **Conditional Spawning:** The script checks the number of existing "fungus_tiny_bad" entities.
*   **Spawn Trigger:** If the count is less than 30, there's a chance (1 in 30) to spawn a new "fungus_tiny_bad" entity.
*   **Entity Creation:** Uses `EntityLoad` to instantiate a new "fungus_tiny.xml" entity at the spawner's location.
*   **Self-Destruction:** The spawner entity itself is killed (`EntityKill`) after its logic is executed.

## Key Attributes/Elements

*   `EntityGetWithTag("fungus_tiny_bad")`: Retrieves all entities currently tagged as "fungus_tiny_bad".
*   `#rats < 30`: The condition that triggers the potential spawn. If the number of "fungus_tiny_bad" entities is less than 30, the spawning logic proceeds.
*   `Random(1, 30) == 5`: The random chance to spawn. This evaluates to true approximately 3.33% of the time when the count is below 30.
*   `EntityLoad("data/entities/animals/fungus_tiny.xml", x, y)`: The function responsible for creating a new entity. It loads the "fungus_tiny.xml" file at the spawner's coordinates (`x`, `y`).
*   `EntityKill(entity_id)`: Removes the spawner entity from the game world after its task is complete.

## Usage Notes

This script is designed to be attached to an entity that acts as a "fungus powder bad" spawner. It ensures a dynamic population of these entities without overwhelming the game.