---
title: Random Cape Initialization
category: scripts
---

# Random Cape Initialization

This script initializes a randomly selected cape for an item entity in Noita. It determines the cape's properties based on a predefined list and applies them to the entity's components.

## Key Functionality

The script performs the following actions:

1.  **Entity Identification and Seeding:**
    *   Retrieves the current entity's ID.
    *   Gets the entity's transform (position).
    *   Sets a random seed based on the entity's position to ensure consistent random outcomes for the same entity.

2.  **Cape Definition:**
    *   A table `capes` defines the available cape types. Each cape entry includes:
        *   `kind`: A string identifier for the cape's effect (e.g., "protection_fire", "breath_underwater").
        *   `name`: The display name of the cape (e.g., "Fire protection cape").
        *   `sprite`: The base name of the sprite file associated with the cape.

3.  **Random Cape Selection:**
    *   The `random_from_array` utility function is used to select one cape from the `capes` table at random.

4.  **Sprite Assignment:**
    *   Determines the sprite file path for the selected cape.
    *   Defaults to `data/items_gfx/cape/default.xml`.
    *   If a specific `sprite` is defined for the chosen cape, it constructs the path as `data/items_gfx/cape/[cape.sprite].xml`.

5.  **Component Editing:**
    *   **`VariableStorageComponent`:** Updates the `value_string` variable to store the `kind` of the selected cape. This is crucial for the game to recognize and apply the cape's effect.
    *   **`ItemComponent`:** Sets the `item_name` to the display name of the selected cape.
    *   **`SpriteComponent`:** Assigns the determined sprite file path to the `image_file` attribute, visually representing the cape.

## Key Attributes Highlighted

*   **`kind`**: The core identifier for the cape's gameplay effect.
*   **`name`**: The user-facing name of the cape.
*   **`sprite`**: Links the cape to its visual representation.
*   **`VariableStorageComponent.value_string`**: Stores the `kind` for gameplay logic.
*   **`ItemComponent.item_name`**: Stores the display name.
*   **`SpriteComponent.image_file`**: Defines the visual asset.

## Example Cape Definitions

```lua
local capes =
{
	{
		kind = "protection_fire",
		name = "Fire protection cape",
		sprite = "protection_fire",
	},
	{
		kind = "protection_radioactivity",
		name = "Radioactivity protection cape",
		sprite = "protection_radioactivity",
	},
	{
		kind = "breath_underwater",
		name = "Underwater breathing cape",
		sprite = "breath_underwater",
	},
	-- ... potentially more cape definitions
}
```