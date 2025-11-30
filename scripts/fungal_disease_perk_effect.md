---
title: Fungal Disease Perk Effect
category: scripts
---

# Fungal Disease Perk Effect

This script defines the behavior for the Fungal Disease perk in Noita. When this perk is active, it has a chance to spawn spore pods or spore pod spikes around the player.

## Core Functionality

The script determines the type and quantity of projectiles to spawn based on a random number generated each frame.

### Projectile Spawning Logic

The `Random(1, 10)` function is used to decide which action to take:

*   **`rnd == 10`**: A single `spore_pod.xml` projectile is spawned.
*   **`rnd > 6`**: Five `spore_pod_spike.xml` projectiles are spawned.
*   **`rnd > 3`**: Two `spore_pod_spike.xml` projectiles are spawned.

### Projectile Properties

The spawned projectiles have randomized velocities.

*   **`spore_pod.xml`**:
    *   `vel_x`: Randomly between -100 and 100.
    *   `vel_y`: Randomly between -100 and 100.
*   **`spore_pod_spike.xml`**:
    *   `vel_x`: Randomly between -400 and 400.
    *   `vel_y`: Randomly between -400 and 100.

## Key Elements

*   **`entity_id`**: The ID of the entity this script is attached to (likely the player).
*   **`root_id`**: The root entity ID, used for spawning projectiles.
*   **`x`, `y`**: The current position of the entity.
*   **`SetRandomSeed`**: Initializes the random number generator based on entity position and game frame for deterministic randomness.
*   **`Random()`**: Generates random numbers for determining spawn events and projectile velocities.
*   **`shoot_projectile()`**: A utility function (likely from `gun_action_utils.lua`) used to spawn projectiles.

## Dependencies

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/gun/procedural/gun_action_utils.lua`

## Projectile Definitions (Referenced)

*   `data/entities/misc/perks/spore_pod.xml`
*   `data/entities/misc/perks/spore_pod_spike.xml`

---