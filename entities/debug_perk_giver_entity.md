---
title: Debug Perk Giver Entity
category: entities
---

# Debug Perk Giver Entity

This entity is a debug tool designed to grant the player all available perks. It is intended for development and testing purposes.

## Entity Structure

The `give_all_perks.xml` file defines a single entity with the following key components:

### LuaComponent

This component is responsible for executing the perk-granting logic.

*   **`script_source_file`**: `data/scripts/perks/give_all_perks.lua` - Specifies the Lua script that handles the perk distribution.
*   **`execute_on_added`**: `1` - The script will execute immediately when the entity is added to the game world.
*   **`execute_every_n_frame`**: `-1` - The script will only execute once.
*   **`execute_times`**: `1` - Confirms that the script execution is limited to a single time.

### LifetimeComponent

This component determines how long the entity persists in the game world.

*   **`lifetime`**: `5` - The entity will exist for 5 seconds before being removed.

## Usage

This entity is typically spawned in-game through console commands or other debug mechanisms to quickly test perk interactions and combinations. It is not intended for use in standard gameplay.