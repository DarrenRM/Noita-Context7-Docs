---
title: Potion Mimics Puzzle Logic
category: biome
---

# Potion Mimics Puzzle Logic

This script defines the logic for the Potion Mimics puzzle found in certain biomes. It manages the spawning of indicators, tracks player progress, and ultimately rewards the player upon completion.

## Core Functionality

The script's primary purpose is to:

*   **Spawn Indicators:** Visually represent the puzzle's progress by spawning small indicators.
*   **Track Awoken Mimics:** Increment a global counter (`potion_mimics_awoken`) as players interact with or "awaken" mimics.
*   **Grant Reward:** Spawn a special item (`SEA_MIMIC`) and unlock a related perk (`card_unlocked_sea_mimic`) once a certain number of mimics are awoken.

## Key Variables and Globals

The script relies on several global variables to maintain state across game sessions and player interactions.

### Local Variables

*   `entity_id`: The unique identifier for the entity running this script.
*   `x`, `y`: The world coordinates of the entity.
*   `indicator_positions`: A table defining the relative positions where indicators will spawn.
*   `px`, `py`: Offset values used to position indicators relative to the puzzle's origin.
*   `awoken_needed`: The target number of "awoken" mimics required to complete the puzzle.

### Global Variables Managed

*   `potion_mimics_awoken`: Stores the total number of mimics that have been "awoken" by the player. This is the primary progress tracker.
*   `potion_mimics_indicators`: Tracks how many indicators have been spawned for the current puzzle instance.
*   `potion_mimics_reward_spawned`: A flag indicating whether the reward for completing the puzzle has already been spawned.

## Puzzle Progression Logic

The script executes its logic when the entity is loaded.

### Indicator Spawning

The script checks the current `indicator_count` against `awoken` and `awoken_needed`. If more indicators need to be spawned, it iterates through the `indicator_positions` table, spawns a `potion_mimic_indicator.xml` entity at the calculated position, and increments `indicator_count`.

*   **Condition:** `indicator_count < awoken and indicator_count < awoken_needed`
*   **Action:**
    *   Calculate indicator position.
    *   Increment `indicator_count` and update the global value.
    *   Load `data/biome_impl/static_tile/potion_mimic_indicator.xml`.
    *   If `awoken > 5`, add a `music_energy_100_near` tag to the entity, potentially affecting ambient music.

### Reward Spawning

Once the puzzle is completed (i.e., `awoken >= awoken_needed`) and the reward hasn't been spawned yet, the script checks for player proximity before spawning the reward.

*   **Conditions:**
    *   At least one player is present (`#players > 0`).
    *   `awoken >= awoken_needed`.
    *   `reward_spawned ~= "1"`.
    *   Player is within 200 units of the puzzle's origin.
*   **Actions:**
    *   Load a particle effect: `data/entities/particles/image_emitters/magical_symbol.xml`.
    *   Play a sound effect: `data/audio/Desktop/projectiles.snd` with the key `player_projectiles/crumbling_earth/create`.
    *   Spawn the reward item: `CreateItemActionEntity("SEA_MIMIC", sx, sy)`.
    *   Unlock a persistent perk: `AddFlagPersistent("card_unlocked_sea_mimic")`.
    *   Set `potion_mimics_reward_spawned` to `"1"` to prevent multiple rewards.

## Dependencies

*   `data/scripts/lib/utilities.lua`: Provides utility functions.
*   `data/biome_impl/static_tile/temples_common.lua`: Likely contains common logic for temple-related entities, including the `RegisterSpawnFunction` override.
*   `data/biome_impl/static_tile/potion_mimic_indicator.xml`: The entity definition for the puzzle indicators.
*   `data/entities/particles/image_emitters/magical_symbol.xml`: The particle effect for the reward.

## Example Usage (for Modders)

Modders can influence this puzzle by:

*   **Modifying `awoken_needed`:** Change the difficulty by adjusting how many mimics need to be awoken.
*   **Altering `indicator_positions`:** Change the visual layout of the indicators.
*   **Customizing Reward:** Replace `SEA_MIMIC` with a different item or entity.
*   **Adjusting Proximity Check:** Modify the `200` unit threshold for reward spawning.
*   **Interacting with Globals:** Ensure custom mimic entities correctly update `potion_mimics_awoken` via `GlobalsSetValue`.