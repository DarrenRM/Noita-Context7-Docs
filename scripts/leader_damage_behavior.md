---
title: Leader Damage Behavior
category: scripts
---

# Leader Damage Behavior

This script defines the behavior of a "leader" entity when it receives damage. Specifically, it handles the spawning of "minions" (in this case, `scavenger_grenade.xml`) when the leader's health drops below certain thresholds.

## Key Functionality

The core logic resides within the `damage_received` function, which is triggered whenever the entity takes damage.

### `damage_received( damage, desc, entity_who_caused, is_fatal )`

This function is called when the entity takes damage.

*   **`damage`**: The amount of damage being dealt.
*   **`desc`**: A string describing the damage source (e.g., "fire", "explosion").
*   **`entity_who_caused`**: The ID of the entity that caused the damage.
*   **`is_fatal`**: A boolean indicating if this damage is fatal.

### Minion Spawning Logic

The script calculates when to spawn minions based on the leader's health and a predefined interval.

*   **`minion_count`**: The total number of minions to potentially spawn.
*   **`minion_interval`**: The health threshold at which a minion should be spawned. This is calculated as `max_health / minion_count`.
*   **`nearest_interval`**: The next health threshold that, if crossed by taking damage, will trigger a minion spawn.
*   **`limit`**: A maximum limit on the number of minions that can be spawned from a single damage event to prevent excessive spawning.

### Spawning Mechanics

When a minion spawn condition is met:

1.  **Sound Effect**: The `duplicate` sound is played.
2.  **Spawn Location Calculation**:
    *   A random distance (`x`) and direction are chosen for the spawn point.
    *   A raytrace is performed to find the nearest platform to avoid spawning in mid-air.
    *   The spawn position is adjusted based on the raytrace result to be on or near the platform.
3.  **Entity Loading**:
    *   `data/entities/animals/scavenger_grenade.xml` is loaded at the calculated spawn position.
    *   `data/entities/particles/teleportation_target.xml` is loaded at the same position, likely for visual feedback.

## Key Attributes/Components Involved (Conceptual)

While this script directly manipulates entity loading and sound, it implicitly interacts with the entity's `DamageModelComponent` to retrieve health information.

*   **`DamageModelComponent`**: This component is assumed to be present on the entity and contains `hp` (current health) and `max_hp` (maximum health) attributes. The script uses `edit_component` to access these values.

## Example Usage (Conceptual)

This script would be attached to an entity that acts as a "leader" or a boss. When this leader takes damage, it will periodically spawn `scavenger_grenade` entities around itself.

```lua
-- Example of how this script might be attached to an entity in its .xml file:
-- <entity name="leader_entity">
--     <components>
--         <DamageModelComponent hp="100" max_hp="100" />
--         <ScriptComponent script_filename="data/scripts/animals/leader_damage.lua" />
--         <!-- Other components -->
--     </components>
-- </entity>
```