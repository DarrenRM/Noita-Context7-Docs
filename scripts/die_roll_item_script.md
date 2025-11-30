---
title: Die Roll Item Script
category: scripts
---

# Die Roll Item Script

This script defines the behavior for the "Die Roll" item in Noita. When triggered, it checks for nearby players and displays a message.

## Core Functionality

The primary function `roll()` is responsible for the item's core logic. It's designed to be called when the item is activated or its state changes.

### `roll()` Function

This function executes the main logic of the Die Roll item.

1.  **Entity Identification:** Gets the current entity's ID and its position.
2.  **Variable Storage Check:** It looks for a `VariableStorageComponent` attached to the entity.
3.  **"rolling" Variable:** Specifically checks for a variable named "rolling" within the storage.
    *   If the "rolling" variable's integer value is `0` (indicating it hasn't rolled yet):
        *   **Player Proximity Check:** It searches for entities with the tag "player\_unit" within a radius of 480 units.
        *   **Message Display:** If one or more players are found within the radius, it displays the game message `$item_die_roll`.
    *   **State Update:** Sets the "rolling" variable's integer value to `1` to prevent repeated rolls.
4.  **Sprite Animation:** Updates the `SpriteComponent` to use the "roll" animation.

## Triggering Mechanisms

The `roll()` function can be invoked through several events:

### `damage_received()`

This function is called when the entity receives damage. It directly calls `roll()` to trigger the item's effect.

### `enabled_changed(entity_id, is_enabled)`

This function is called when the enabled state of the entity changes.
*   If `is_enabled` is `true`, it calls `roll()`.

### `kick()`

This function is called when the entity is kicked. It directly calls `roll()` to trigger the item's effect.

## Key Components and Attributes

*   **`VariableStorageComponent`**: Used to store the state of the "rolling" variable.
    *   `name`: "rolling"
    *   `value_int`: Tracks if the roll has already occurred (0 = not rolled, 1 = rolled).
*   **`SpriteComponent`**: Controls the visual appearance.
    *   `rect_animation`: Set to "roll" when the item is activated.
*   **`EntityGetInRadiusWithTag()`**: A utility function to find nearby entities.
    *   Radius: `480`
    *   Tag: `"player_unit"`
*   **`GamePrint()`**: Displays in-game messages.
    *   Message ID: `$item_die_roll`