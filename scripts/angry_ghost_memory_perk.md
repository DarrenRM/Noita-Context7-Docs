---
title: Angry Ghost Memory Perk
category: scripts
---

# Angry Ghost Memory Perk

This script implements the "Angry Ghost Memory" perk in Noita. When the player picks up this perk, it stores the `projectile_file` name of a random projectile within a certain radius. If the perk's cooldown has expired, it will then attempt to spawn a projectile of the stored type.

## Key Functionality

### Projectile Memory

*   **`projectile_memory` (VariableStorageComponent):** This component stores the `projectile_file` name of the last projectile encountered.
*   **`projectile_file` (VariableStorageComponent):** This is the name of the projectile file to be stored.

### Cooldown Mechanism

*   **`angry_ghost_cooldown` (VariableStorageComponent):** This component manages the cooldown for the perk.
    *   **`value_int`:** Represents the remaining cooldown ticks. When this value reaches 0, the perk can trigger.

### Triggering Logic

1.  **Entity Identification:** The script first identifies the player's entity.
2.  **Projectile Scan:** It searches for any entities tagged as "projectile" within a 48-unit radius around the player.
3.  **Random Selection:** If projectiles are found, one is randomly selected.
4.  **Memory Storage:** The `projectile_file` from the selected projectile's `VariableStorageComponent` is extracted and stored in the player's `projectile_memory` component.
5.  **Cooldown Check:** The `angry_ghost_cooldown` is decremented if it's greater than 0.

## Important Attributes

*   **Radius for Projectile Detection:** 48 units.
*   **Target Component for Projectile Name:** `VariableStorageComponent` with `name` set to `"projectile_file"`.
*   **Storage Component for Perk Memory:** `VariableStorageComponent` with `name` set to `"projectile_memory"`.
*   **Cooldown Component:** `VariableStorageComponent` with `name` set to `"angry_ghost_cooldown"`.

## Example Usage (Conceptual)

While this script defines the perk's behavior, its integration into the game would involve:

*   **Perk Definition:** This Lua script would be referenced in a perk definition file (e.g., `perks.xml`).
*   **Entity Spawning:** The player entity would need to have the `angry_ghost_cooldown` and `projectile_memory` `VariableStorageComponent`s attached when the perk is acquired.
*   **Triggering Mechanism:** A separate game system would likely be responsible for checking the cooldown and calling this script's logic when appropriate (e.g., on player damage, or at specific intervals).

This script focuses solely on the memory and cooldown aspects of the "Angry Ghost Memory" perk. The actual spawning of the remembered projectile would be handled by another part of the game's logic, triggered when the cooldown is ready.