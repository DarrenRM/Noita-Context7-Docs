---
title: Egg Entity Damage Behavior
category: scripts
---

# Egg Entity Damage Behavior

This script defines the behavior of an "egg" entity when it receives damage.

## Key Functionality

### `damage_received` Function

This function is triggered when the egg entity takes damage.

*   **Parameters:**
    *   `damage`: The amount of damage received.
    *   `desc`: A description of the damage.
    *   `entity_who_caused`: The entity that caused the damage.
    *   `is_fatal`: A boolean indicating if the damage is fatal.

*   **Core Logic:**
    *   Retrieves the entity's ID and position.
    *   Sets a random seed based on game frame and entity position for deterministic randomness.
    *   With a 60% probability (`Random(0, 100) < 60`), it spawns a `boss_dragon.xml` entity.
    *   The spawned dragon is positioned slightly above the egg's location (`pos_y - 16`).

## Key Attributes/Elements

*   **Entity Spawning:** The primary effect of damage is the potential to spawn a boss dragon.
*   **Randomness:** The spawning event is governed by a pseudo-random number generator, making it not guaranteed on every hit.
*   **Positioning:** The spawned entity's position is relative to the egg's location.

## Example Usage (Conceptual)

This script would be attached to an entity definition (e.g., in an XML file) that represents an egg. When this egg entity is hit by any damage source in the game, the `damage_received` function will execute.

```lua
-- Example of how this script might be referenced in an entity XML:
-- <entity name="egg_entity">
--   <components>
--     <component name="script_component" filename="data/scripts/buildings/egg.lua" />
--     ... other components ...
--   </components>
-- </entity>
```