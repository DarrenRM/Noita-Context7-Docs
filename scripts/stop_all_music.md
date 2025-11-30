---
title: Stop All Music
category: scripts
---

---

# Stop All Music

This script provides a simple function to immediately stop all currently playing music in Noita and clear the music queue.

## Function: `stop()`

This function is the core of the script. When called, it executes the game's built-in function to fade out and dequeue all music.

### Key Functionality

*   **`GameTriggerMusicFadeOutAndDequeueAll()`**: This is the primary game function called by `stop()`. It handles the immediate cessation of all music playback and empties the music playback queue.

## Usage

To use this script, you would typically call the `stop()` function from another Lua script or a debug console command.

**Example:**

```lua
-- In another script:
dofile_once("data/scripts/debug/music_stop_all.lua")

-- To stop all music:
stop()
```