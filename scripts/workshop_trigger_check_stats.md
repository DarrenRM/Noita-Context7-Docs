---
title: Workshop Trigger Check Stats
category: scripts
---

# Workshop Trigger Check Stats

This script defines the logic for checking player statistics within the workshop to determine rewards. It's primarily used to grant rewards based on player actions, such as pacifism.

## Core Functionality: `collision_trigger()`

This function is called when a collision event occurs, likely related to entering or exiting the workshop area. It checks specific player statistics to decide which rewards to grant.

### Key Statistics Checked:

*   **`enemies_killed`**: This statistic is crucial. It's retrieved using `StatsBiomeGetValue("enemies_killed")`.
    *   **Important Distinction**: `StatsBiomeGetValue()` tracks stats *since the last call to `StatsResetBiome()`*. The `workshop_exit` function typically calls `StatsResetBiome()`, making `StatsBiomeGetValue()` ideal for tracking actions within a specific workshop session.
    *   In contrast, `StatsGetValue()` tracks global player statistics.

### Reward Logic:

The script implements a conditional reward system based on the `enemies_killed` count:

1.  **Pacifist Reward (No Enemies Killed)**:
    *   If `enemies_killed` is `0`, the player is considered a pacifist for this session.
    *   A random treasure chest (`chest_random.xml`) is spawned.
    *   The chest's name is changed to `$item_chest_treasure_pacifist` to indicate a pacifist reward.
    *   The chest is spawned at the player's current location or at a designated `workshop_reference` entity if found.

2.  **Standard Reward (Enemies Killed)**:
    *   If `enemies_killed` is greater than `0`, the pacifist reward is *not* granted. The script currently doesn't explicitly define alternative rewards for this case, implying a default behavior or that other scripts handle these rewards.

### Helper Functions Used:

*   `GetUpdatedEntityID()`: Retrieves the ID of the entity that triggered the event.
*   `EntityGetTransform(entity_id)`: Gets the X and Y coordinates of an entity.
*   `StatsBiomeGetValue(stat_name)`: Retrieves the value of a biome-specific statistic.
*   `EntityGetClosestWithTag(x, y, tag)`: Finds the closest entity with a given tag.
*   `EntityLoad(entity_file_path, x, y)`: Loads an entity from an XML file at specified coordinates.
*   `change_entity_ingame_name(entity_id, new_name)`: Changes the in-game display name of an entity.

### Configuration Notes:

*   The script relies on the presence of a `workshop_reference` entity for precise spawning of rewards if the player's exact location is not desired.
*   The `print()` statements are for debugging and can be removed in production builds.