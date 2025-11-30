---
title: Tower Check Script
category: scripts
---

---

# Tower Check Script

This script is designed to be attached to an entity that acts as a trigger within the game world. It checks for the presence of specific entities within a radius and, based on what it finds, triggers various game events, unlocks, and entity spawns.

## Core Functionality

The script's primary purpose is to detect nearby entities with specific tags and execute different actions accordingly.

### Key Checks and Actions

The script prioritizes checks in the following order:

1.  **`small_friend` Check:**
    *   **Condition:** If an entity with the tag `small_friend` is found within a 16-unit radius.
    *   **Actions:**
        *   Creates an item action entity with the ID `NUKE_GIGA`.
        *   Adds a persistent flag `card_unlocked_nukegiga`.
        *   Loads the entity `data/entities/projectiles/deck/nuke.xml` at the current position.
        *   Adds a persistent flag `final_secret_orb`.
        *   Kills the triggering entity.

2.  **`big_friend` Check:**
    *   **Condition:** If an entity with the tag `big_friend` is found within a 16-unit radius (and the `small_friend` check failed).
    *   **Actions:**
        *   Creates an item action entity with the ID `BOMB_HOLY_GIGA`.
        *   Adds a persistent flag `card_unlocked_bomb_holy_giga`.
        *   Loads the entity `data/entities/projectiles/deck/nuke.xml` at the current position.
        *   Adds a persistent flag `final_secret_orb2`.
        *   Kills the triggering entity.

3.  **Greed Curse Check:**
    *   **Condition:** If the game has the `greed_curse` flag set, does *not* have the `greed_curse_gone` flag set, and an entity with the tag `player_unit` is found within a 16-unit radius.
    *   **Actions:**
        *   Creates an item action entity with the ID `DIVIDE_10`.
        *   Adds a persistent flag `card_unlocked_divide`.
        *   Kills the triggering entity.

4.  **`player_unit` Check (Default):**
    *   **Condition:** If an entity with the tag `player_unit` is found within a 16-unit radius (and all previous checks failed).
    *   **Actions:**
        *   Creates an item action entity with the ID `AIR_BULLET`.
        *   Kills the triggering entity.

## Key Attributes and Elements

*   **`entity_id`**: The unique identifier for the entity this script is attached to.
*   **`x`, `y`**: The world coordinates of the triggering entity.
*   **`EntityGetInRadiusWithTag(x, y, radius, tag)`**: A function that searches for entities with a specific `tag` within a given `radius` around `(x, y)`.
*   **`CreateItemActionEntity(action_id, x, y)`**: Spawns a special entity that performs an action, identified by `action_id`.
*   **`AddFlagPersistent(flag_name)`**: Sets a game flag that persists across game sessions.
*   **`EntityLoad(entity_path, x, y)`**: Loads a new entity from its XML definition at the specified coordinates.
*   **`EntityKill(entity_id)`**: Destroys the specified entity.
*   **`GameHasFlagRun(flag_name)`**: Checks if a specific game flag is currently active.

## Usage Notes

*   This script is intended to be attached to a projectile or a static entity that can detect nearby units.
*   The order of `if/elseif` statements is crucial, as it determines the priority of actions.
*   The `radius` for entity detection is fixed at 16 units.
*   The script is designed to be self-terminating by calling `EntityKill(entity_id)` after its actions are performed.