---
title: Failed Alchemist Orb Spawner
category: scripts
---

---

# Failed Alchemist Orb Spawner

This script is responsible for spawning a "Failed Alchemist" entity when a specific orb is interacted with.

## Core Functionality

*   **Entity Spawning:** Upon activation, the script loads and spawns `data/entities/animals/failed_alchemist_b.xml` at the orb's location.
*   **Sound Effect:** Plays a distinct "statue appear" sound from the `animals.bank` audio file.
*   **Entity Modification:** The spawned "Failed Alchemist" entity is given a `VariableStorageComponent` with the tag `no_gold_drop`, preventing it from dropping gold.
*   **Self-Destruction:** The original orb entity that triggered the script is immediately killed.

## Key Components

*   `EntityLoad`: Used to instantiate the `failed_alchemist_b.xml` entity.
*   `GamePlaySound`: Triggers the audio cue for the alchemist's appearance.
*   `EntityAddComponent`: Adds a `VariableStorageComponent` to modify the spawned entity's behavior.
*   `EntityKill`: Removes the orb entity after it has served its purpose.