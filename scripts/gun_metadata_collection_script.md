---
title: Gun Metadata Collection Script
category: scripts
---

# Gun Metadata Collection Script

This script is responsible for collecting and registering metadata for guns in Noita. It iterates through defined actions, creates shots, and registers their associated information with the game.

## Core Functionality

The script's primary purpose is to facilitate the creation and registration of gun data. It leverages the `gun.lua` script for core gun functionalities.

### Key Steps:

1.  **Initialization:**
    *   `dofile("data/scripts/gun/gun.lua")`: Loads the main gun script.
    *   `reflecting = true`: A flag likely used to indicate the metadata collection phase.
    *   `ConfigGunShotEffects_Init( shot_effects )`: Initializes shot effect configurations.

2.  **Action Iteration:**
    *   The script loops through a table named `actions`. Each element in this table represents a specific gun action.
    *   `current_reload_time = 0`: Resets reload time for each action.
    *   `local shot = create_shot()`: Creates a new shot object.
    *   `c = shot.state`: Accesses the state of the created shot.
    *   `set_current_action( action )`: Sets the current action being processed.
    *   `action.action()`: Executes the actual logic defined within the current action.

3.  **Metadata Registration:**
    *   `register_action( c )`: This is the crucial step where the collected information about the shot and its associated action is registered with the game's internal systems.

4.  **Finalization:**
    *   `reflecting = false`: Resets the flag after all actions have been processed.

## Important Variables and Functions:

*   `actions`: A table containing definitions for various gun actions. Each action likely has an `action()` function that defines its behavior.
*   `create_shot()`: A function that instantiates a new shot object.
*   `set_current_action( action )`: Sets the currently active action for processing.
*   `register_action( state )`: Registers the metadata of a processed action/shot with the game.
*   `reflecting`: A boolean flag used to control the metadata collection process.