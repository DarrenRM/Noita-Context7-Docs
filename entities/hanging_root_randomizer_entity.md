---
title: Hanging Root Randomizer Entity
category: entities
---

# Hanging Root Randomizer Entity

This entity is responsible for randomly selecting and applying a hanging root variation. It utilizes a Lua script to manage the randomization process.

## Key Components

### LuaComponent

This component executes a Lua script upon the entity's addition.

*   **`script_source_file`**: `data/scripts/props/hanging_root_verlet_randomizer.lua` - The script that handles the randomization logic.
*   **`execute_on_added`**: `1` - The script will execute as soon as the entity is added to the game world.
*   **`execute_every_n_frame`**: `-1` - The script will only execute once.
*   **`execute_times`**: `1` - Confirms the script executes only a single time.

### AudioComponent

This component defines audio events associated with the entity.

*   **`file`**: `data/audio/Desktop/materials.bank` - Specifies the audio bank containing the sound events.
*   **`event_root`**: `collision/vine` - The root event name for sounds related to vine collisions.