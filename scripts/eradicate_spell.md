---
title: Eradicate Spell
category: scripts
---

# Eradicate Spell

This script implements a spell that eradicates all non-player "mortal" entities within its range.

## Functionality

The `eradicate.lua` script performs the following actions:

### Key Attributes

*   **Targeting:** Selects entities with the "mortal" tag.
*   **Exclusion:** Explicitly excludes entities tagged as "player_unit".
*   **Damage Check:** Verifies if the target entity possesses a `DamageModelComponent`. This implies the entity is capable of taking damage and thus can be "eradicated".
*   **Entity Elimination:** If an entity meets the criteria (mortal, not player, has damage component), it is immediately killed using `EntityKill()`.

### Script Logic

1.  **Get Entity ID:** Retrieves the unique identifier for the entity executing this script.
2.  **Get Position:** Obtains the world coordinates (x, y) of the executing entity.
3.  **Find Mortal Entities:** Iterates through all entities in the game world that have the "mortal" tag.
4.  **Player Exclusion:** For each mortal entity, it checks if it also has the "player_unit" tag. If it does, it's skipped.
5.  **Damage Component Check:** For remaining mortal entities, it attempts to find a `DamageModelComponent`.
6.  **Eradication:** If a `DamageModelComponent` is found, the entity is killed.