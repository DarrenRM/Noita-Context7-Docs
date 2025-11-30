---
title: Homunculus Biome Check Perk
category: scripts
---

# Homunculus Biome Check Perk

This script governs the behavior of the "Homunculus" perk, specifically how it interacts with different biomes and player progression. It manages the spawning of homunculus entities based on biome, depth, and a memory system to prevent excessive spawning in the same areas.

## Key Functionality

*   **Biome Detection:** Identifies the current biome the player is in.
*   **Depth Tracking:** Records the player's current depth.
*   **Homunculus Spawning:** Spawns a homunculus entity when specific conditions are met.
*   **Spawn Limiting:** Prevents spawning if the player has already reached a certain limit of homunculi.
*   **Memory System:** Tracks recently visited biomes to avoid repeated spawning in the same location.

## Core Components & Logic

This script relies on a `VariableStorageComponent` attached to the entity it's associated with. This component stores the perk's state.

### State Variables

The script manages several key variables, primarily stored within the `VariableStorageComponent`:

| Variable Name   | Type    | Description