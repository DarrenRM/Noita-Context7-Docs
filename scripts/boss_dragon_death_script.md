---
title: Boss Dragon Death Script
category: scripts
---

# Boss Dragon Death Script

This script defines the behavior and effects that occur when the boss dragon entity is defeated in Noita. It handles item drops, persistent flags, and the spawning of special orbiting entities.

## Key Functions and Logic

### `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )`

This is the primary function called when the boss dragon dies.

*   **`entity_id`**: The unique identifier for the boss dragon entity.
*   **`pos_x`, `pos_y`**: The coordinates where the dragon was defeated.

### Effects and Item Spawns

*   **Health Pickup**: Spawns a `heart.xml` pickup at the dragon's death location.
*   **Wand Drop**: Spawns a `wand_unshuffle_06.xml` wand.

### Persistent Flags

*   **`AddFlagPersistent( "miniboss_dragon" )`**: Sets a persistent flag indicating the miniboss dragon has been defeated.
*   **`AddFlagPersistent( "card_unlocked_dragon" )`**: Sets a persistent flag indicating a specific card related to the dragon has been unlocked.

### Special Orbiting Entity Spawning

The script dynamically spawns special orbiting entities based on whether the `card_unlocked_dragon` flag is active.

*   **`check_parallel_pos( pos_x )`**: A utility function (likely from `utilities.lua`) to determine a parallel position for seeding the random number generator.
*   **`SetRandomSeed( pw, 540 )`**: Initializes the random number generator for consistent, yet varied, spawns.

#### Orbiting Entity Options

The available orbiting entities are defined in tables:

*   **Default Options**:
    *   `ORBIT_DISCS`
    *   `ORBIT_FIREBALLS`
    *   `ORBIT_NUKES`
    *   `ORBIT_LASERS`
    *   `ORBIT_LARPA`

*   **Options when `card_unlocked_dragon` is true**:
    *   `ORBIT_DISCS`
    *   `ORBIT_FIREBALLS`
    *   `ORBIT_LASERS`
    *   `ORBIT_LARPA`
    *   (Note: `ORBIT_NUKES` is excluded in this case)

#### Spawning Logic

*   The script spawns a set number of orbiting entities (`count`).
*   It randomly selects an entity from the available `opts` table.
*   The selected entity is spawned using `CreateItemActionEntity`.
*   The chosen entity is removed from the `opts` table to prevent duplicates in a single spawn sequence.

### Summary of Key Elements

| Element                 | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `death()` function      | Core logic for dragon's demise.                                          |
| `heart.xml`             | Spawns a health pickup.                                                  |
| `wand_unshuffle_06.xml` | Spawns a specific wand.                                                  |
| `miniboss_dragon` flag  | Persistent flag for miniboss defeat.                                     |
| `card_unlocked_dragon` flag | Persistent flag for card unlock.                                         |
| `ORBIT_DISCS`           | Spawns orbiting discs.                                                   |
| `ORBIT_FIREBALLS`       | Spawns orbiting fireballs.                                               |
| `ORBIT_NUKES`           | Spawns orbiting nukes (conditional).                                    |
| `ORBIT_LASERS`          | Spawns orbiting lasers.                                                  |
| `ORBIT_LARPA`           | Spawns orbiting larpa.                                                   |
| Random selection        | Ensures variety in spawned orbiting entities.                            |
| Conditional spawning    | Adjusts spawned entities based on player progress (`card_unlocked_dragon`). |