---
title: InventoryGuiComponent Documentation for AI-Assisted Modding
source: https://noita.wiki.gg/wiki/Documentation:InventoryGuiComponent
category: modding-wiki
---

# InventoryGuiComponent Documentation

This document details the `InventoryGuiComponent` in Noita, a crucial element for understanding and modifying how the game's inventory and UI elements function. For modders, grasping this component is essential for creating custom inventory UIs, managing item displays, and integrating new functionalities that interact with the player's inventory.

## Overview

The `InventoryGuiComponent` is a fundamental part of Noita's graphical user interface (GUI) system, specifically responsible for rendering and managing the player's inventory. It dictates how items are displayed, how the inventory grid is structured, and how interactions with inventory slots occur. Modding this component allows for significant customization of the player experience, from visual changes to complex inventory management systems.

## Core Functionality

The `InventoryGuiComponent` handles the visual representation of the player's inventory. This includes:

*   **Displaying Items:** Rendering item icons, names, and quantities within inventory slots.
*   **Inventory Grid:** Managing the layout and size of the inventory grid.
*   **Slot Interactions:** Handling clicks, drags, and other user interactions with inventory slots.
*   **Item Stacking:** Visualizing and managing stacked items.

## Component Properties and Methods

While the original wiki page had no specific text, in a typical Noita modding context, understanding the properties and methods of `InventoryGuiComponent` would be vital. These would likely include:

*   **Properties:**
    *   `grid_width`: The number of columns in the inventory grid.
    *   `grid_height`: The number of rows in the inventory grid.
    *   `slot_size`: The dimensions of each individual inventory slot.
    *   `items`: A list or table containing the items currently in the inventory.
*   **Methods:**
    *   `AddItem(item_data)`: Adds an item to the inventory.
    *   `RemoveItem(item_id)`: Removes an item from the inventory.
    *   `UpdateDisplay()`: Refreshes the visual representation of the inventory.
    *   `HandleInput(input_event)`: Processes user input related to the inventory.

**Note:** Specific properties and methods would be discovered through reverse engineering or by consulting detailed API documentation if available.

## Modding Examples (Conceptual)

Modding the `InventoryGuiComponent` often involves scripting to alter its behavior or appearance. Here are conceptual examples of what might be achieved:

### Example 1: Customizing Inventory Grid Size

This example demonstrates how one might attempt to increase the inventory grid size using Lua scripting.

```lua
-- This is a conceptual example. Actual implementation may vary.

local function modify_inventory_grid()
    -- Find the InventoryGuiComponent entity
    local inventory_entity = Game.GetInventoryGuiComponent() -- Hypothetical function

    if inventory_entity then
        -- Increase grid dimensions (e.g., to 10x10)
        inventory_entity.grid_width = 10
        inventory_entity.grid_height = 10

        -- Potentially re-calculate slot positions or update the display
        inventory_entity.UpdateDisplay() -- Hypothetical function
    end
end

-- Call the function to apply changes
modify_inventory_grid()
```

### Example 2: Adding a Custom Item Display

This example illustrates how a mod might add a custom visual element or information to an item when it's displayed in the inventory.

```lua
-- This is a conceptual example. Actual implementation may vary.

local function draw_custom_item_info(slot_entity, item_data)
    -- Check if the item has custom data we want to display
    if item_data.custom_mod_info then
        -- Draw some custom text or icon next to the item
        local x, y = slot_entity.GetPosition() -- Hypothetical function
        Screen:DrawText(x + 20, y + 20, "MODIFIED", 1, 1, 1, 1) -- Hypothetical drawing function
    end
end

-- This function would need to be hooked into the InventoryGuiComponent's rendering loop.
-- For instance, by overriding or extending a drawing method.
```

## Related Components and Concepts

*   **`GuiComponent`**: The base class for all GUI elements in Noita. `InventoryGuiComponent` inherits from this.
*   **`ItemComponent`**: Represents individual items within the game, which are then displayed by the `InventoryGuiComponent`.
*   **Entity System**: Understanding how entities and their components interact is crucial for manipulating GUI elements.
*   **Lua Scripting**: The primary language for modding Noita, used to interact with game components.

## Further Resources

*   [Lua API](https://noita.wiki.gg/wiki/Modding:_Lua_API)
*   [Entity System Documentation](https://noita.wiki.gg/wiki/Modding:_Entity_System)
*   [Noita Modding Discord](https://discord.gg/noitamodding) (for community support and specific questions)