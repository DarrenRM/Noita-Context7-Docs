---
title: Orb 07 Trap Item Script
category: scripts
---

# Orb 07 Trap Item Script

This script defines the behavior of a specific item in Noita, likely an "orb" that triggers an event when picked up. The primary function is `item_pickup`, which, when executed, spawns various enemy groups at predefined locations. The script utilizes helper functions to determine which enemy groups to spawn based on procedural randomness.

## Key Functions

### `item_pickup(entity_item, entity_who_picked, item_name)`

This is the core function that is called when the item is picked up by a player. It contains commented-out logic for spawning entities. The active logic (though commented out in the provided raw data) would determine the type and quantity of enemies to spawn based on a random seed.

### `spawn_group(names, x, y)`

This function takes a list of entity names and coordinates. It spawns each entity in the list at the given `x` and `y` coordinates, with a slight horizontal offset between each spawned entity. It also has a chance to "double spawn" the group, meaning each entity in the list will be spawned twice.

### `get_random_group(seed)`

This function returns a table of entity names that represent a specific enemy group. The group selected is determined by a procedural random number generated using the provided `seed`. Different ranges of the random number map to different combinations of enemies, ranging from scavengers to powerful "the_end" entities and various wizards.

## Key Attributes and Elements

The script primarily focuses on entity spawning logic. The key elements are:

*   **Entity Loading:** Uses `EntityLoad` to instantiate entities from their XML definitions.
*   **Procedural Randomness:** Employs `ProceduralRandomf` to introduce variability in which enemy groups are spawned and how many.
*   **Predefined Spawn Locations:** Uses hardcoded coordinates (`x_near_shore`, `y_near_shore`, etc.) for spawning enemies.
*   **Enemy Group Definitions:** The `get_random_group` function defines several distinct enemy compositions.
*   **Conditional Spawning:** The commented-out logic in `item_pickup` shows conditional spawning based on random chance, allowing for different spawn scenarios.

## Example Usage (Conceptual based on commented-out code)

When the `orb_07_trap.lua` item is picked up:

1.  A random number is generated.
2.  Based on this number, different sets of enemy groups are selected using `get_random_group`.
3.  The `spawn_group` function is called multiple times to spawn these groups at specific locations like `x_near_shore`, `x_far_shore`, and `x_cave`.
4.  There's a small chance to spawn a large amount of loose chunks, or even a group of sheep.

```lua
-- Example of how spawn_group might be called (based on commented-out code)
spawn_group( get_random_group(1), x_near_shore, y_near_shore )
spawn_group( get_random_group(2), x_far_shore, y_far_shore )
```

## Summary of Enemy Groups (from `get_random_group`)

| Random Range | Enemy Group                                                              |
| :----------- | :----------------------------------------------------------------------- |
| < 0.2        | `scavenger_leader`, `scavenger_smg`, `scavenger_grenade`, `scavenger_mine` |
| < 0.3        | `the_end/gazer`                                                          |
| < 0.4        | `tentacler`, `tentacler_small`, `tentacler_small`                        |
| < 0.5        | `the_end/bloodcrystal_physics`                                           |
| < 0.6        | `crypt/crystal_physics`, `crypt/crystal_physics`                         |
| < 0.7        | `crypt/phantom_a`, `crypt/phantom_a`, `crypt/phantom_b`                  |
| < 0.8        | `vault/lasershooter`, `vault/acidshooter`                                |
| < 0.9        | `drone_lasership`, `drone_lasership`, `drone_lasership`                  |
| else         | `wizard_poly`, `wizard_tele`, `wizard_swapper`, `wizard_dark`            |

## Notes for Modding

*   The core logic for spawning is within the `item_pickup` function.
*   To modify the spawned enemies, you would primarily edit the `get_random_group` function or the entity names within its return tables.
*   The spawn locations are hardcoded; changing these would alter where the enemies appear.
*   The `spawn_group` function's double-spawn mechanic can be adjusted by changing the `0.25` probability.
*   The commented-out section in `item_pickup` provides a good starting point for understanding how to implement different spawn scenarios based on probabilities.