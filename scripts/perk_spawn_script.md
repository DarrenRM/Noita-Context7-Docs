---
title: Perk Spawn Script
category: scripts
---

# Perk Spawn Script

This script handles the spawning of perks within the game. It's a simple entity script designed to be attached to an entity that will trigger the perk spawning mechanism.

## Core Functionality

The primary purpose of this script is to call the `perk_spawn_random` function, which is responsible for selecting and spawning a random perk at the entity's current location.

### Key Functions

*   `perk_spawn_random(x, y)`: This function, likely defined in `data/scripts/game_helpers.lua`, is the core of the perk spawning logic. It takes the entity's X and Y coordinates as input to determine where the perk should appear.

## Script Structure

The script is minimal and relies on external game helper functions.

### Dependencies

*   `data/scripts/game_helpers.lua`: Provides essential game utility functions, including `perk_spawn_random`.
*   `data/scripts/lib/utilities.lua`: A general utility library, potentially used for other helper functions.
*   `data/scripts/perks/perk.lua`: Likely contains definitions and logic related to perks themselves.

### Execution Flow

1.  **Get Entity ID and Transform**: The script first retrieves the ID of the entity it's attached to and its current X, Y coordinates.
2.  **Spawn Perk**: It then calls `perk_spawn_random` with the obtained coordinates.
3.  **Kill Entity**: Finally, the entity that triggered the perk spawn is immediately killed, as its purpose is fulfilled.

## AI Modding Considerations

When modding this script, the primary area of interest is the `perk_spawn_random` function. Understanding how it selects perks and its parameters will be crucial for:

*   **Custom Perk Spawning**: Modifying the logic to spawn specific custom perks or to influence the probability of certain perks appearing.
*   **Triggering Conditions**: Integrating this script with other custom entities or events to trigger perk spawns under unique circumstances.
*   **Perk Distribution**: Adjusting how perks are distributed throughout the game world.