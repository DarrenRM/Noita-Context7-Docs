---
title: Noita Initialization and Weather Script
category: scripts
---

# Noita Initialization and Weather Script

This script (`init.lua`) handles the core initialization of the Noita game world, including setting up weather patterns and defining key game events. It acts as a central hub for various game systems.

## Core Game Initialization

The script begins by loading essential utility functions and biome modifier configurations. It then defines several callback functions that are triggered by specific game events.

### Key Event Callbacks

These functions are hooks into the game's lifecycle, allowing mods to inject custom behavior at critical moments.

*   **`OnMagicNumbersAndWorldSeedInitialized()`**: Called when magic numbers and the world seed are initialized. This is a crucial point for mods that rely on these values.
*   **`OnBiomeConfigLoaded()`**: Triggered after biome configurations are loaded. This is where biome-specific modifiers are initialized.
*   **`OnWorldPreUpdate()`**: Executed before each world update. This is used for continuous processes like weather updates.
*   **`OnPlayerDied( player_entity )`**: Called when the player character dies. It handles inventory cleanup and triggers the game over sequence.
*   **`OnCountSecrets()`**: Returns the total number of secrets and the number of secrets found by the player. This is important for tracking player progression.

## Weather System

The script implements a dynamic weather system that can generate snow, rain, and other atmospheric effects.

### Weather Configuration

The weather system is defined by several tables that specify the properties of different weather types.

*   **`snow_types`**: Defines various types of snow, including their chance of occurring, material, particle count, duration, and visual effects.
    *   `chance`: Probability of this specific snow type occurring.
    *   `rain_material`: The material that falls as snow (e.g., "snow", "slush").
    *   `rain_particles_min`/`max`: Range for the number of particles emitted.
    *   `rain_duration`: How long the snow lasts (in frames, or -1 for indefinite).
    *   `rain_draw_long_chance`: Chance for the rain to be drawn as longer streaks.
    *   `rain_type`: Enum indicating the type of precipitation (e.g., `RAIN_TYPE_SNOW`).
*   **`rain_types`**: Defines different types of liquid rain, including water, blood, acid, and slime. Properties are similar to `snow_types`.

### Weather Implementation

The `weather_init` and `weather_update` functions manage the weather system.

*   **`weather_init( year, month, day, hour, minute )`**:
    *   Initializes the weather for the current in-game date and time.
    *   Determines whether it's snowing or raining based on the month and a random chance.
    *   Selects a specific weather type from the configured tables.
    *   Applies biome modifiers (e.g., "FREEZING") based on the weather.
    *   Sets fog and cloud density.
    *   Configures the `WorldStateComponent` to reflect the weather.
*   **`weather_update()`**:
    *   Called every frame before the world updates.
    *   Checks if the weather needs to be re-initialized (e.g., new day).
    *   Emits rain or snow particles using `GameEmitRainParticles` if the weather conditions and duration are met.

### Weather Constants

*   **`RAIN_TYPE_NONE`**: No precipitation.
*   **`RAIN_TYPE_SNOW`**: Snowfall.
*   **`RAIN_TYPE_LIQUID`**: Liquid precipitation (rain, blood, acid, etc.).

## Helper Functions

*   **`pick_random_from_table_backwards( t, rnd )`**: A utility function to pick a random element from a table based on its `chance` attribute, iterating backwards.
*   **`weather_check_duration()`**: Checks if the current weather effect has exceeded its duration.

## Other Game Logic

*   **`OnPlayerDied( player_entity )`**:
    *   `GameDestroyInventoryItems( player_entity )`: Clears the player's inventory.
    *   `GameTriggerGameOver()`: Initiates the game over sequence.
*   **`OnCountSecrets()`**:
    *   Calculates the total number of secrets (orbs + special flags) and the number of secrets the player has found.
    *   Uses `GameGetOrbCountTotal()`, `GameGetOrbCountAllTime()`, and `HasFlagPersistent()` to track progress.