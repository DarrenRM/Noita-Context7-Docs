---
title: Perk Gamble Spawn Script
category: scripts/perks
---

# Perk Gamble Spawn Script

This script handles the spawning and selection logic for the "Gamble" perk in Noita. When a player encounters this perk, it attempts to spawn two other random perks. If a "Gamble" perk is spawned again, it is discarded, and a new one is attempted until a non-"Gamble" perk is successfully picked up.

## Key Functionality

*   **Perk Spawning:** Utilizes `perk_spawn_random(x, y)` to generate random perks at the player's location.
*   **Gamble Perk Reroll:** Checks the `perk_id` of the spawned perk. If it's "GAMBLE", the spawned perk is killed (`EntityKill(pid)`) and a new one is attempted.
*   **Perk Pickup:** If the spawned perk is not "GAMBLE", it is picked up by the player using `perk_pickup(pid, player, "", false, false)`.
*   **Spawn Count:** The script aims to spawn and successfully pick up a total of `count = 2` non-"Gamble" perks.
*   **Self-Destruction:** The script entity itself is killed (`EntityKill(entity_id)`) once its task is complete.

## Core Logic Breakdown

The script iterates twice (`while count > 0 do`) to ensure two perks are acquired. Inside the loop:

1.  A random perk is spawned.
2.  The `perk_id` of the spawned perk is read.
3.  If the `perk_id` is not "GAMBLE":
    *   The perk is picked up by the player.
    *   The `count` is decremented, moving towards loop completion.
4.  If the `perk_id` *is* "GAMBLE":
    *   The spawned "Gamble" perk entity is destroyed.
    *   The loop continues to try spawning another perk without decrementing `count`.

This ensures that the player always receives two distinct, non-"Gamble" perks from this interaction.