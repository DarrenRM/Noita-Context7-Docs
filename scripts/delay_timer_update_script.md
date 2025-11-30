---
title: Delay Timer Update Script
category: scripts
---

---

# Delay Timer Update Script

This script is designed to update a visual timer displayed on an entity. It decrements a "lifetime" value stored in a `VariableStorageComponent` and formats the remaining time into a human-readable string for display in a `SpriteComponent`.

## Key Components and Functionality

### Entity Identification

-   `GetUpdatedEntityID()`: Retrieves the unique identifier for the entity that this script is attached to and currently updating.

### Timer Logic

-   **`VariableStorageComponent`**: This component is crucial for storing the timer's state.
    -   **`lifetime`**: A variable within `VariableStorageComponent` that holds the remaining time in seconds (as an integer).
    -   The script reads the current `lifetime`, decrements it by 1 (simulating one second passing), and ensures it doesn't go below zero.
    -   The updated `lifetime` is then written back to the `VariableStorageComponent`.

### Time Formatting

-   The script calculates the number of full minutes (`s`) and remaining seconds (`ms`) from the `timeleft`.
-   It then formats these values into a string suitable for display.
    -   Minutes are converted to a string.
    -   Seconds are padded with leading zeros to ensure a two-digit format (e.g., "05" instead of "5").
-   `GameTextGet("$format_timer", stext, mstext)`: This function is used to construct the final display string, likely using a predefined format that combines minutes and seconds.

### Visual Update

-   **`SpriteComponent`**: This component is responsible for rendering the visual representation of the entity, including text.
    -   `edit_component( entity_id, "SpriteComponent", function(comp,vars) ... end)`: This function targets the `SpriteComponent` of the entity.
    -   `vars.text = final`: The formatted timer string (`final`) is assigned to the `text` property of the `SpriteComponent`.
    -   `EntityRefreshSprite( entity_id, comp )`: This command ensures that the visual update to the `SpriteComponent` is applied and rendered on screen.

## Usage Notes

-   This script assumes that an entity has a `VariableStorageComponent` with a variable named "lifetime" (of type integer) and a `SpriteComponent` capable of displaying text.
-   The `$format_timer` localization string is expected to be defined elsewhere in the game's data to control the exact appearance of the timer display.