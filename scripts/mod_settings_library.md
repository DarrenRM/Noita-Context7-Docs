---
title: Mod Settings Library
category: scripts
---

# Mod Settings Library

This library provides functions for defining, displaying, and managing mod settings within Noita. It allows modders to create configurable options for their mods that can be accessed and modified by players through the game's mod settings menu.

## Core Concepts

### Setting Scopes

Settings can have different scopes, determining when their values are applied:

*   **`MOD_SETTING_SCOPE_NEW_GAME` (0):** Changes are applied only after a new game run is started.
*   **`MOD_SETTING_SCOPE_RUNTIME_RESTART` (1):** Changes are applied upon the next game executable restart.
*   **`MOD_SETTING_SCOPE_RUNTIME` (2):** Changes are applied immediately.
*   **`MOD_SETTING_SCOPE_ONLY_SET_DEFAULT` (3):** Used internally to indicate no changes should be applied.

### Setting Types

The library supports various types of settings, automatically generating UI elements based on their default values:

*   **Boolean:** Toggles (On/Off).
*   **Number:** Sliders with defined minimum, maximum, and default values.
*   **Enum (String):** Dropdown menus with predefined string options.
*   **Text:** Input fields for string values.
*   **Title:** Displays a text title, often used for section headers.
*   **Image:** Displays an image.
*   **Vertical Spacing:** Adds vertical space in the UI.

### Categories and Foldable Sections

Settings can be organized into categories, which can be made foldable in the UI to improve organization.

## Key Functions

### `mod_settings_gui(mod_id, settings, gui, in_main_menu)`

This is the primary function for rendering the mod settings UI. It iterates through a list of `settings` and draws the appropriate UI elements based on their type and configuration.

*   **`mod_id`**: The unique identifier of the mod.
*   **`settings`**: A table containing the definitions of the mod's settings and categories.
*   **`gui`**: The GUI object to draw on.
*   **`in_main_menu`**: A boolean indicating if the UI is being displayed in the main menu.

### `mod_settings_update(mod_id, settings, init_scope)`

This function is responsible for initializing and applying mod setting values. It's called at various game events (init, new game, unpause).

*   **`mod_id`**: The unique identifier of the mod.
*   **`settings`**: A table containing the definitions of the mod's settings.
*   **`init_scope`**: The scope to consider when applying settings.

### `mod_setting_tooltip(mod_id, gui, in_main_menu, setting)`

Helper function to display tooltips for settings, including information about when changes will take effect.

## Setting Definition Structure

A setting is defined as a Lua table with the following key attributes:

| Attribute           | Type                               | Description