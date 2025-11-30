---
title: Workshop Exit Logic
category: scripts
---

# Workshop Exit Logic

This script defines the behavior when a player interacts with a workshop exit, triggering a collapse and cleanup of workshop-related entities.

## Core Functionality: `collision_trigger()`

This function is executed when the workshop exit is activated.

### Key Actions:

*   **Biome Reset:** Resets biome statistics using `StatsBiomeReset()`.
*   **Entity Spawning:**
    *   Spawns `workshop_collapse.xml` at a specific offset.
    *   Spawns two instances of `workshop_areadamage.xml` at defined offsets.
*   **Workshop Entity Destruction:**
    *   Destroys entities tagged with "workshop" using `EntityGetClosestWithTag` and `EntityKill`. Multiple calls ensure all workshop entities are removed.
    *   Destroys entities tagged with "workshop\_show\_hint" to remove any associated hints.
*   **Temple Area Checker Cleanup:**
    *   Identifies and destroys "temple\_areachecker" entities within a radius.
    *   Filters these checkers to only destroy those on a similar horizontal level to the workshop exit.
*   **Global State Update:**
    *   Sets a global value indicating the temple has collapsed, using a dynamically generated name based on the workshop's position (`TEMPLE_COLLAPSED_` + `temple_pos_to_id`).
    *   Deactivates the temple using `temple_set_active_flag`.
*   **Audio and Music:**
    *   Initiates a music fade-out and dequeues all music tracks over 2 seconds.
    *   Plays a specific sound effect (`misc/temple_collapse`) at a defined position.

### Important Notes:

*   The script relies on helper functions from `utilities.lua` and `temple_shared.lua`.
*   The exact positions for spawning and the offsets for destruction are hardcoded.
*   The `temple_pos_to_id` function (not provided in this snippet) is crucial for generating unique global variable names.