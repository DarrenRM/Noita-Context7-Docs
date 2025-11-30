---
title: Workshop Exit Final Logic
category: scripts
---

# Workshop Exit Final Logic

This script defines the behavior when the player interacts with the final workshop exit, triggering a sequence of events that lead to the collapse of the workshop area and the activation of the final boss arena.

## Core Functionality

The primary function `collision_trigger()` is executed when the entity associated with this script is collided with.

### Key Actions Performed:

*   **Biome Statistics Reset:** Calls `StatsBiomeReset()` to reset biome-specific statistics.
*   **Entity Spawning:**
    *   Spawns `workshop_collapse.xml` at a specific offset.
    *   Spawns two instances of `workshop_areadamage.xml` at different offsets to create damaging zones.
*   **Workshop Entity Destruction:**
    *   Identifies and destroys multiple entities tagged with "workshop" using `EntityGetClosestWithTag`. This ensures the workshop structure is removed.
    *   Destroys an entity tagged with "workshop_show_hint" to remove any lingering hints.
*   **Temple Area Checker Cleanup:**
    *   Finds all entities tagged with "temple_areachecker" within a radius.
    *   Kills any "temple_areachecker" entities that are on approximately the same horizontal level as the exit.
*   **Audio and Music:**
    *   Initiates a music fade-out and dequeues all music tracks over 2 seconds using `GameTriggerMusicFadeOutAndDequeueAll`.
    *   Plays a specific sound effect (`misc/temple_collapse`) using `GamePlaySound`.
*   **Temple State Management:**
    *   Sets an active flag for the temple area using `temple_set_active_flag`.
    *   Sets a global variable `FINAL_BOSS_ARENA_ENTERED` to "1" using `GlobalsSetValue`, indicating the final boss arena has been accessed.
*   **Self-Destruction:** The script's own entity is destroyed using `EntityKill( entity_id )`.

### Dependencies:

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/biomes/temple_shared.lua`

### Key Entities Spawned:

*   `data/entities/misc/workshop_collapse.xml`
*   `data/entities/misc/workshop_areadamage.xml`

### Key Tags Used:

*   `workshop`
*   `workshop_show_hint`
*   `temple_areachecker`

### Key Global Variables Modified:

*   `FINAL_BOSS_ARENA_ENTERED`