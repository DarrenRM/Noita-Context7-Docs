---
title: Plague Rat Spawner
category: scripts/animals
---

# Plague Rat Spawner

This script is responsible for spawning additional "plague rats" in the game world under specific conditions.

## Core Functionality

*   **Conditional Spawning:** The script checks the current number of existing "plague_rat" entities. If there are fewer than 30, it has a chance to spawn a new one.
*   **Random Chance:** The spawning of a new rat is determined by a random roll (`Random(1, 20) == 5`). This means there's a 1 in 20 chance of spawning a rat each time the script runs, provided the population limit hasn't been reached.
*   **Entity Loading:** If the conditions are met, the script loads the `plague_rats_rat.xml` entity at the current position of the spawner.
*   **Self-Destruction:** After its logic is executed, the spawner entity (`entity_id`) is immediately killed, ensuring it doesn't persist unnecessarily.

## Key Attributes

*   **`plague_rat` Tag:** This tag is crucial for identifying existing plague rat entities to enforce the population limit.
*   **Population Limit:** `30` - The maximum number of plague rats allowed before new ones stop spawning.
*   **Spawn Chance:** `Random(1, 20) == 5` - A 5% chance to spawn a rat when the population is below the limit.
*   **Entity to Spawn:** `data/entities/misc/perks/plague_rats_rat.xml` - The specific entity file that defines the plague rat.

## Usage

This script is typically attached to an invisible entity that acts as a trigger or a point in the environment where rats might naturally appear. It's a simple mechanism to dynamically increase the presence of plague rats as the player progresses or explores.