---
title: Orb Map Initialization
category: scripts
---

# Orb Map Initialization

This script initializes the orb map in Noita. It checks if an orb map string already exists in the game's global variables. If not, it calls `orb_map_update()` to generate one. Otherwise, it prints the existing orb map string to the console.

## Core Functionality

*   **Global Variable Check:** The script first checks for the existence of a global variable named `"ORB_MAP_STRING"`.
*   **Initialization Trigger:** If `"ORB_MAP_STRING"` is empty (meaning the orb map hasn't been generated yet), the `orb_map_update()` function is called.
*   **Existing Map Handling:** If `"ORB_MAP_STRING"` already contains data, the script prints this existing string to the console, indicating that the orb map is already set up.

## Key Functions

### `orb_map_update()`

This function (defined elsewhere) is responsible for generating and setting the `"ORB_MAP_STRING"` global variable. Its internal logic is not detailed in this specific script.

## Usage Notes

*   This script is typically run once at the start of a game session or when a new game is initiated.
*   The `utilities.lua` library is a dependency, suggesting it provides helper functions for global variable manipulation or other game system interactions.