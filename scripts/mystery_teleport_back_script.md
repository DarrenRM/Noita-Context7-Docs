---
title: Mystery Teleport Back Script
category: scripts
---

# Mystery Teleport Back Script

This script defines the behavior for a "mystery teleport back" mechanism in Noita. When activated, it triggers a music fade-out and dequeues all music, while also persistently setting a flag named "secret_tower".

## Key Functions

### `portal_teleport_used()`

This function is called when the mystery teleport is activated.

*   **`GameTriggerMusicFadeOutAndDequeueAll( 5.0 )`**: Initiates a fade-out of the current music over 5.0 seconds and clears the music queue.
*   **`AddFlagPersistent( "secret_tower" )`**: Adds a persistent flag to the game state. This flag, "secret_tower", can be used by other game systems or mods to track or trigger events related to this teleport.