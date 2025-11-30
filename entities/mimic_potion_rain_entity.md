---
title: Mimic Potion Rain Entity
category: entities
---

# Mimic Potion Rain Entity

This entity defines the behavior for a "mimic potion rain" effect in Noita. It's primarily controlled by a Lua script that handles the spawning of mimic potions.

## Key Components

### `LifetimeComponent`

*   **`lifetime`**: The duration in frames this entity will exist.
    *   Value: `75`
*   **`serialize_duration`**: How long the entity's state should be saved.
    *   Value: `1`

### `LuaComponent`

This component is responsible for executing the custom logic for the mimic potion rain.

*   **`_enabled`**: Whether the Lua script is active.
    *   Value: `1` (enabled)
*   **`execute_every_n_frame`**: The frequency (in frames) at which the script's `on_frame` function will be called.
    *   Value: `20`
*   **`script_source_file`**: The path to the Lua script that controls the entity's behavior.
    *   Value: `data/scripts/buildings/spawn_mimic_potion_rain.lua`

## Lua Script (`data/scripts/buildings/spawn_mimic_potion_rain.lua`)

This script is the core of the mimic potion rain effect. It likely handles:

*   Detecting when to spawn mimic potions.
*   Choosing which potions to spawn.
*   Spawning the potions at appropriate locations.
*   Potentially managing the visual or auditory effects of the rain.