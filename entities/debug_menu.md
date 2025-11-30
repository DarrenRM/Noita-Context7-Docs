---
title: Debug Menu
category: entities
---

# Debug Menu

This document details the functionality of the debug menu script in Noita, designed for modders and developers to test and manipulate various game elements.

## Core Functionality

The debug menu provides a Lua-based interface accessible in-game, allowing for quick access to debugging tools. It's structured around a main menu with various sub-menus for specific functionalities.

### Key Functions

*   **`reload_dofile(filename)`**: Reloads a Lua file, useful for applying changes to scripts without restarting the game.
*   **`gui_do_return_button()`**: Adds a "Return" button to the current GUI frame, allowing navigation back to the previous menu.
*   **`gui_do_close_button()`**: Adds a "Close" button to the current GUI frame, which destroys the debug menu.
*   **`gui_do_button_list(actions, fn_get_name_from_action, fn_action_clicked)`**: A generic function to display a list of buttons, each triggering a specified action. It supports multi-column layouts for better organization.
*   **`gui_fn_main()`**: Renders the main debug menu interface, displaying available options.
*   **`async_loop(...)`**: Manages the game loop for the debug menu, handling GUI updates and frame rendering.

## Debug Menu Options

The `main_menu_items` table defines the core options available in the debug menu.

### Menu Item Structure

Each item in `main_menu_items` is a table with the following key fields:

*   **`ui_name`**: The text displayed for the menu option.
*   **`action`**: A function that is executed when the menu option is selected. This function often changes the `gui_frame_fn` to navigate to a sub-menu or directly performs an action.

### Key Debug Menu Options

*   **Spawn perk**: Opens a sub-menu to spawn any available perk.
*   **Spawn streaming integration event**: Allows triggering specific in-game events.
*   **Teleport player to location**: Provides a list of predefined locations to teleport the player to.
*   **Apply biome modifier to all biomes**: Enables applying biome-specific modifiers globally.
*   **Fade out music**: Triggers a fade-out for the current music track.
*   **Spawn sampo**: Spawns a "sampo" entity at the player's or mouse's location.
*   **Spawn all emerald tablets**: Spawns all available emerald tablet items in a line.
*   **Spawn all enemies that hold wands**: Spawns a variety of enemies, each holding a wand.
*   **Fungal shift**: Initiates a fungal shift event, allowing for material transformations.
*   **Fungal shift to rock**: Converts various liquids and gases to static rock.
*   **Fungal shift from rock**: Converts static rock to water.
*   **Fungal shift water to weird fungus**: Transforms water into fungi.
*   **Fungal shift ambrosia to diamond**: Converts ambrosia to diamond.
*   **Fungal shift ambrosia to acid**: Converts ambrosia to acid.
*   **Fungal shift weird fungus to steam**: Transforms fungi into steam.
*   **Fungal shift blood -> poly**: Converts blood to polymorph liquid.
*   **Fungal shift blood -> toxic sludge**: Converts blood to radioactive liquid.
*   **Spawn apparition**: Spawns an apparition entity.
*   **do_newgame_plus**: Triggers the new game plus sequence.
*   **Spawn good wand**: Spawns a pre-defined "good wand".
*   **ConvertMaterialOnAreaInstantly() - test near camera**: Tests the `ConvertMaterialOnAreaInstantly` function.
*   **Test GameShootProjectile bug**: Tests the `GameShootProjectile` function.
*   **Test GameCreateBeamFromSky()**: Tests the `GameCreateBeamFromSky` function.
*   **Close**: Closes the debug menu.

## Sub-Menu Functions

Several functions are dedicated to rendering specific sub-menus:

*   **`gui_fn_spawn_perk()`**: Displays a list of all perks for spawning.
*   **`gui_fn_spawn_streaming_event()`**: Allows selection and triggering of streaming integration events.
*   **`gui_fn_teleport_to_location()`**: Presents a list of named locations for teleportation.
*   **`gui_fn_biome_modifiers()`**: Lists available biome modifiers that can be applied globally.

## Helper Functions

*   **`gui_frame_fn`**: A global variable that determines which GUI rendering function is currently active.
*   **`gui`**: The main GUI object used for rendering menu elements.
*   **`destroy`**: A boolean flag to signal the destruction of the debug menu.
*   **`menu_pos_x`, `menu_pos_y`**: Define the starting position of the debug menu on the screen.

This script serves as a powerful tool for Noita modders to quickly test game mechanics, spawn entities, and manipulate the game world during development.