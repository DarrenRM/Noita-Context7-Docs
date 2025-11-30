---
title: Lukki Egg Behavior
category: scripts
---

---

# Lukki Egg Behavior

This script defines the behavior of Lukki Eggs in Noita, specifically how they react to damage and potentially spawn Lukki creatures.

## Core Functionality

The primary function of this script is to handle damage events for Lukki Eggs. When the egg receives damage, it has a chance to spawn a smaller "tiny" Lukki.

### Key Attributes and Elements

*   **`spawn_lukki( entity_id, pos_x, pos_y )`**:
    *   This function is responsible for the actual spawning of a Lukki.
    *   It plays a specific sound effect (`lukki_eggs/destroy`).
    *   It loads and places a `lukki_tiny.xml` entity at the egg's position.

*   **`damage_received( damage, desc, entity_who_caused, is_fatal )`**:
    *   This is the main event handler for when the Lukki Egg takes damage.
    *   It retrieves the current entity ID and its position.
    *   It uses a random seed based on game frame and entity position for unpredictable outcomes.
    *   **Spawning Condition**: A Lukki is spawned if:
        *   The damage is fatal (`is_fatal` is true).
        *   OR a random chance (10% or less) is met (`Random(0,100) < 10`).
        *   AND the damage received is greater than a small threshold (`damage > 0.1`).

## AI Modding Considerations

When modding Lukki Eggs, consider the following:

*   **Damage Threshold**: The `damage > 0.1` condition means very minor damage won't trigger a spawn.
*   **Random Chance**: The 10% chance for non-fatal damage introduces an element of unpredictability. This can be adjusted to make eggs more or less likely to hatch.
*   **Lukki Variant**: The script specifically spawns `lukki_tiny.xml`. Modifying this path would allow for different Lukki variants or other entities to be spawned.
*   **Sound Effect**: The `lukki_eggs/destroy` sound can be changed to alter the audio feedback upon hatching.
*   **Fatal Damage**: Any fatal blow will guarantee a Lukki spawn, regardless of the random chance.