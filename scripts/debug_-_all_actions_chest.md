---
title: Debug - All Actions Chest
category: scripts
---

---

# Debug - All Actions Chest

This script creates a chest at the mouse cursor's position that contains all available gun actions. This is a debugging tool to easily test and access various gun functionalities.

## Functionality

The primary function `entity_chest_with_all_actions` is responsible for:

1.  **Loading the Chest Entity:** It loads the `chest.xml` entity at the specified `x` and `y` coordinates.
2.  **Accessing Chest Components:** It retrieves the `ItemChestComponent` from the loaded chest entity.
3.  **Gathering Action IDs:** It iterates through a global `actions` table (presumably populated by `gun_actions.lua`) and concatenates all action IDs into a comma-separated string.
4.  **Setting Chest Actions:** It sets the `actions` property of the `ItemChestComponent` to the generated string, effectively populating the chest with all available actions.

## Key Elements

*   **`entity_chest_with_all_actions( x, y )`**: The main function that orchestrates the creation of the debug chest.
*   **`EntityLoad( "data/entities/items/chest.xml", x, y)`**: Loads the base chest entity.
*   **`EntityGetComponent( entity, "ItemChestComponent" )`**: Retrieves the component responsible for chest behavior and its contents.
*   **`actions`**: A global table (expected to be defined elsewhere, likely in `gun_actions.lua`) containing information about all available gun actions.
*   **`action.id`**: The unique identifier for each gun action.
*   **`ComponentSetValue( components_item_chest[1], "actions", string_actions )`**: The crucial step that assigns the collected action IDs to the chest, making them available to the player.
*   **`DEBUG_GetMouseWorld()`**: Used to get the current mouse cursor's world coordinates for placing the chest.

## Usage

When this script is executed, a chest will appear at the mouse cursor. Interacting with this chest will allow the player to select and use any of the gun actions defined in the game's data.