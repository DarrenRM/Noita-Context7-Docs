---
title: Orb Pickup Logic
category: scripts
---

# Orb Pickup Logic

This script handles the logic for when a player picks up an orb in Noita. It determines the type of orb, applies persistent flags, grants rewards, and displays messages to the player.

## Core Functionality

The `item_pickup` function is the main entry point for this script. It's triggered when an item entity is picked up by another entity (presumably the player).

### Key Attributes & Elements

*   **`entity_item`**: The entity representing the orb being picked up.
*   **`entity_who_picked`**: The entity that picked up the orb (e.g., the player).
*   **`item_name`**: The internal name of the item being picked up (though not directly used in this specific orb logic).
*   **`VariableStorageComponent`**: Used to store custom variables associated with the orb, such as `card_name`.
*   **`OrbComponent`**: Identifies the entity as an orb and stores its unique `orb_id`.
*   **`orb_id`**: A numerical identifier for the orb. Different ranges of `orb_id` trigger different behaviors.
*   **`GameGetOrbCollectedAllTime(orb_id)`**: Checks if an orb with the given ID has been collected in any previous runs.
*   **`GameIsDailyRunOrDailyPracticeRun()`**: Checks if the current game is a daily run.
*   **`AddFlagPersistent(flag_name)`**: Adds a persistent flag to the game state, which can be used for tracking progress across runs.
*   **`EntityLoad(entity_file_path, x, y)`**: Loads a new entity into the game at the specified coordinates. Used for spawning rewards like hearts or special effects.
*   **`GamePrintImportant(title, description)`**: Displays a prominent message to the player.
*   **`shoot_projectile(entity_id, projectile_file_path, x, y, angle, speed)`**: Spawns a projectile effect.
*   **`EntityKill(entity_id)`**: Destroys an entity.

## Orb Types and Rewards

The behavior of the orb pickup is primarily determined by the `orb_id`.

### Special "Outside Bounds" Orbs (`orb_id >= 100`)

*   **Reward**: Grants an "evil heart" (`heart_evil.xml`).
*   **Messages**: Displays "$itempickup_orb_evil" and "$itempickupdesc_orb_discovered".
*   **Flags**: Adds the persistent flag `"progress_orb_evil"`.

### Normal Orbs (`orb_id < 100`)

*   **If already collected or in a daily run**:
    *   **Reward**: Grants a regular heart (`heart.xml`).
    *   **Messages**: Displays "$itempickup_orb_discovered" and "$itempickupdesc_orb_discovered".
*   **If collected for the first time (and not a daily run)**:
    *   **Messages**: Displays "$itempickup_orb" and a description specific to the orb ID (e.g., "$itempickupdesc_orb_01").
    *   **Flags**: Adds a persistent flag like `"progress_orb_pickup_01"`.
    *   **Card Reward**: If the orb has a `card_name` variable stored, it will attempt to create that item action entity.

## Global Orb Progress and Achievements

*   **Total Orb Count**: The script tracks the total number of orbs collected across all runs using `GameGetOrbCountAllTime()`.
*   **"All Orbs" Achievement**: If the total orb count reaches 11 or more, the `"progress_orb_all"` flag is added, and the `"ALL_ORBS"` achievement is granted.

## Boss Centipede Interaction

*   **Scream Effect**: If the "boss_centipede_is_dead" flag is *not* set (meaning the boss hasn't been defeated in the current run), picking up an orb will trigger a special scream effect (`orb_boss_scream.xml`) attached to the player.

## Orb Effect Visuals

*   **Visual Cue**: A visual effect (`orb_effect.xml`) is spawned at the orb's location upon pickup.

## Cleanup

*   **Entity Destruction**: The orb entity itself is destroyed (`EntityKill`) after its logic is processed.