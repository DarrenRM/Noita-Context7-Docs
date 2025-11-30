---
title: Necrobot AI Script
category: scripts
---

# Necrobot AI Script

This script defines the behavior for the "Necrobot" entity in Noita, focusing on its interaction with other entities.

## Core Functionality

The primary purpose of this script is to identify and apply a specific status effect to nearby "mortal" entities that are not the player and do not already have the "necrobot_NOT" tag.

### Key Attributes and Elements

*   **`entity_id`**: Retrieves the unique identifier for the Necrobot entity.
*   **`x`, `y`**: Gets the current position of the Necrobot.
*   **`radius`**: Defines the detection range (144 units) for other entities.
*   **`targets`**: A list of entities within the specified `radius` that possess the "mortal" tag.
*   **`found`**: A boolean flag, though not actively used in the provided snippet, it suggests potential for future logic.

### Target Selection Logic

The script iterates through detected `targets` and applies the following conditions:

*   **Not Player**: `EntityHasTag( v, "player_unit" ) == false` ensures the player is not targeted.
*   **Not Already Processed**: `EntityHasTag( v, "necrobot_NOT" ) == false` prevents re-applying the effect to entities already tagged by this script.
*   **Is Animal Entity**: `string.find( file, "entities/animals/" ) ~= nil` filters targets to specifically be animal entities.

### Effect Application

When a target meets the criteria:

*   **`LuaComponent`**: A `LuaComponent` is added to the target entity.
    *   **`script_death`**: Set to `"data/scripts/status_effects/necrobot.lua"`, indicating the script to run when the target dies.
    *   **`execute_every_n_frame`**: Set to `"-1"`, meaning the script is not intended to execute periodically during the entity's lifetime but rather on specific events (like death).
*   **Particle Effect**: A green sparse tiny spark particle effect (`tinyspark_green_sparse.xml`) is spawned at the Necrobot's location.
*   **Child Entity**: The spawned particle effect is added as a child to the targeted entity.
*   **`necrobot_NOT` Tag**: The `necrobot_NOT` tag is added to the target entity to mark it as processed by this Necrobot.