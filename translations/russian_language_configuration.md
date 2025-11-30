---
title: Russian Language Configuration
category: translations
---

# Russian Language Configuration

This document details the configuration for the Russian language in Noita, focusing on font and UI element settings.

## Language Attributes

The `<Language>` tag defines the primary settings for a specific language.

| Attribute | Description |
|---|---|
| `name` | The display name of the language (e.g., "русский"). |
| `font_default` | Path to the default font used for most in-game text. |
| `font_inventory_title` | Path to the font used for inventory titles. |
| `font_important_message_title` | Path to the font used for important message titles. |
| `font_world_space_message` | Path to the font used for messages displayed in the game world. |
| `fonts_utf8` | Flag indicating UTF-8 font support (1 for enabled). |
| `fonts_pixel_font` | Flag indicating pixel font support (1 for enabled). |
| `ui_action_info_offset2` | UI offset value for action information. |
| `ui_wand_info_offset1` | UI offset value for wand information. |
| `ui_wand_info_offset2` | UI offset value for wand information. |

## Font Paths

The following are the key font files used for the Russian language:

*   **Default Font:** `data/fonts/font_pixel.xml`
*   **Inventory Title Font:** `data/fonts/font_pixel_big.xml`
*   **Important Message Title Font:** `data/fonts/font_pixel_huge.xml`
*   **World Space Message Font:** `data/fonts/font_pixel.xml`

## UI Offsets

These values control the positioning of certain UI elements.

*   `ui_action_info_offset2`: 45
*   `ui_wand_info_offset1`: 55
*   `ui_wand_info_offset2`: 60