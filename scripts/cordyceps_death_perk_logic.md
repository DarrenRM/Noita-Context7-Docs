---
title: Cordyceps Death Perk Logic
category: scripts
---

# Cordyceps Death Perk Logic

This script defines the behavior of the "Cordyceps" perk when the player dies. It spawns small fungal entities based on the number of times this perk has been picked up.

## Core Functionality

The `death` function is triggered upon player death and handles the spawning of fungal entities.

### Key Attributes

*   **`damage_type_bit_field`**: Bitmask representing the type of damage taken.
*   **`damage_message`**: String message associated with the damage.
*   **`entity_thats_responsible`**: The entity that caused the damage.
*   **`drop_items`**: Boolean indicating if items should be dropped.

### Fungal Entity Spawning Logic

1.  **Perk Pickup Count**: It retrieves a global value `FUNGI_PERK_TOTAL_COUNT` to determine how many times the Cordyceps perk has been picked up.
2.  **Rat Count Calculation**: The number of fungal entities to spawn (`rat_count`) is calculated based on the `pickup_count`, with a maximum of 10.
3.  **Spawn Condition**: Fungal entities are only spawned if the current number of existing "perk\_fungus\_tiny" tagged entities is less than 30.
4.  **Randomized Spawning**: Within the loop, there's a 50% chance (`rnd > 50`) to spawn a `fungus.xml` entity at the player's death location.