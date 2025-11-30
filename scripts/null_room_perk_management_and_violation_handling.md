---
title: Null Room Perk Management and Violation Handling
category: scripts
---

---

# Null Room Perk Management and Violation Handling

This script handles the logic for a "null room" mechanic in Noita, primarily focusing on managing player perks and responding to violations of the null room's rules. It includes functions for permanently polymorphing entities, handling perk duplication attempts, and removing all player perks under specific conditions.

## Key Functions

### `permapolymorph_entity(entity_id)`

This function permanently polymorphs a given entity. It searches for various "POLYMORPH" game effects attached to the entity and, if found, sets their duration to `-1` (infinite).

### `nullroom_polymorph_violation(entity_id)`

This function is triggered when a player attempts to duplicate perks, likely through polymorphing. It implements a "gods are angry" mechanic with increasing severity based on the number of violations.

*   **Parallel World Violations:** In parallel worlds, there's a 50% chance of applying a permanent polymorph to the player and a message indicating increased divine anger. A global counter `PARALLEL_POLYMORPH_VIOLATIONS` is incremented.
*   **General Violations:** A global counter `POLYMORPH_VIOLATIONS` tracks total violations.
*   **Punishment:** Depending on the violation count and random chance, the player might be permanently polymorphed, and a more aggressive entity (like an angry Steve) is spawned.
*   **Entity Spawning:** An angry Steve entity is spawned near the player's location, with a berserk effect applied.

### `nullroom_remove_all_perks()`

This function is responsible for removing all perks from the player. It first attempts to find the active player. If the player is not found directly, it searches for entities tagged as "polymorphed\_player" or "polymorphed\_cessation" and calls `nullroom_polymorph_violation` on them if found.

## Main Logic

The script's main execution block checks for the presence of at least three entities tagged with `"null_room_check"`. If this condition is met:

1.  **Music Trigger:** A specific music event (`music/oneshot/heaven_02_no_drs`) is triggered.
2.  **Persistent Flag:** A persistent flag `"secret_null"` is added.
3.  **Visual Effect:** A "supernova" particle effect is spawned.
4.  **Perk Management:** All player perks are created and then immediately removed using `nullroom_remove_all_perks()`.
5.  **Message Display:** An important message (`$log_curse_secret`) is displayed to the player.
6.  **Cleanup:** All entities tagged with `"null_room_check"` are destroyed.

## Debug Function

### `DEBUG_REMOVE_ALL_PERKS()`

This function appears to be a debug version of the main null room logic, intended for testing. It triggers the same music, visual effects, perk management, and messages, but it uses the camera position for effects and doesn't rely on the `"null_room_check"` entities.