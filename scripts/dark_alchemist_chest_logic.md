---
title: Dark Alchemist Chest Logic
category: scripts
---

# Dark Alchemist Chest Logic

This script defines the behavior of the "Dark Alchemist Chest" in Noita. It interacts with an "Alchemist Key" to determine its state and unlock specific rewards.

## Core Functionality

The chest's primary function is to dispense powerful items or a selection of items based on the state of a nearby "Alchemist Key".

### Interaction with Alchemist Key

*   **Detection:** The chest detects "Alchemist Key" entities within a 24-unit radius.
*   **Key Status Check:** It reads a "status" variable from the `VariableStorageComponent` of the detected key.
    *   `status == 2`: Indicates the key is in a state to unlock the chest.
*   **Persistent Flag:** The chest uses a persistent flag `card_unlocked_alchemy` to track if it has been opened for the first time.

## Chest States and Rewards

### First Time Opening (`status == 2` and `card_unlocked_alchemy == false`)

When opened for the first time with the correct key status, the chest provides a set of powerful, specific items and permanently unlocks the "alchemy card".

*   **Messages:** Displays `$log_alchemist_chest_open` and `$logdesc_alchemist_chest_open`.
*   **Item Dispensation:** Creates the following items at specific positions relative to the chest:
    *   `ALL_ACID`
    *   `ALL_NUKES`
    *   `ALL_DISCS`
    *   `ALL_ROCKETS`
    *   `ALL_BLACKHOLES`
    *   `ALL_DEATHCROSSES`
*   **Flag Update:** Sets `card_unlocked_alchemy` to `true`.
*   **Visual/Audio Effects:**
    *   Spawns `main_swirly_red.xml` particle explosion.
    *   Spawns `circle_blood.xml` projectile.
    *   Plays `misc/chest_dark_open` sound.

### Subsequent Openings (`status == 2` and `card_unlocked_alchemy == true`)

If the chest is opened again with the correct key status, it dispenses a random selection of items.

*   **Messages:** Displays `$log_alchemist_chest_opened` and `$logdesc_alchemist_chest_opened`.
*   **Item Dispensation:** Randomly selects and dispenses 3 items from the following pool:
    *   `ALL_ACID`
    *   `ALL_NUKES`
    *   `ALL_DISCS`
    *   `ALL_ROCKETS`
    *   `ALL_BLACKHOLES`
    *   `ALL_DEATHCROSSES`
*   **Visual/Audio Effects:** Similar to the first opening, but without the specific "unlock" messages.

## Cleanup

*   **Key Removal:** The Alchemist Key entity is destroyed (`EntityKill( key_id )`).
*   **Chest Removal:** The chest entity itself is destroyed (`EntityKill( entity_id )`).
*   **Persistent Flag:** Sets `secret_chest_dark` to `true` to mark that this specific dark chest has been interacted with.

## Key Components and Variables

*   `entity_id`: The unique identifier for the chest entity.
*   `x`, `y`: The coordinates of the chest entity.
*   `keys`: A table containing detected "Alchemist Key" entities.
*   `key_id`: The ID of the first detected "Alchemist Key".
*   `variables`: The `VariableStorageComponent` of the Alchemist Key.
*   `status`: An integer representing the state of the Alchemist Key (specifically `2` for chest interaction).
*   `already_done`: A boolean indicating if the `card_unlocked_alchemy` flag is set.
*   `opts`: A table of item names available for random selection.
*   `rnd`: A random integer used to select an item from `opts`.