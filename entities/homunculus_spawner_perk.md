---
title: Homunculus Spawner Perk
category: entities
---

# Homunculus Spawner Perk

This entity defines the behavior for the "Homunculus Spawner" perk in Noita. It's responsible for periodically checking the player's current biome and potentially spawning a homunculus.

## Key Components

### `VariableStorageComponent`

This component is used to store various states and data related to the perk:

*   **`name="status"`**: Likely indicates the active state of the perk (e.g., `value_int="1"` for enabled).
*   **`name="latest_depth"`**: Stores the player's depth when the perk was last checked or updated.
*   **`name="memory"`**: A string variable, potentially used for storing specific biome-related information or flags.

### `LuaComponent`

This is the core of the perk's logic.

*   **`_enabled="1"`**: Ensures the Lua script is active.
*   **`execute_every_n_frame="60"`**: The associated Lua script (`homunculus_check_biome.lua`) will be executed every 60 frames. This controls the frequency of biome checks.
*   **`script_source_file="data/scripts/perks/homunculus_check_biome.lua"`**: Points to the external Lua script that contains the actual logic for checking biomes and spawning homunculi.

## Tags

*   **`greed_curse`**: This tag suggests a potential connection to the "Greed" curse or a similar mechanic, possibly influencing when or how this perk is acquired or behaves.