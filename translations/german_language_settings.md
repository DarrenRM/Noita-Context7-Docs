---
title: German Language Settings
category: translations
---

# German Language Settings

This document details the configuration for the German language in Noita, focusing on font definitions and UI offsets.

## Language Configuration

The `<Language>` tag defines the primary settings for a specific language.

### Key Attributes

*   **`name`**: The display name of the language.
*   **`font_default`**: Path to the default font used for general text.
*   **`font_inventory_title`**: Path to the font used for inventory titles.
*   **`font_important_message_title`**: Path to the font used for important message titles.
*   **`font_world_space_message`**: Path to the font used for messages displayed in the game world.
*   **`fonts_utf8`**: Flag indicating if UTF-8 font support is enabled (1 for enabled).
*   **`fonts_pixel_font`**: Flag indicating if pixel font rendering is enabled (1 for enabled).
*   **`ui_action_info_offset2`**: Offset value for UI elements related to action information.
*   **`ui_wand_info_offset1`**: Offset value for UI elements related to wand information.
*   **`ui_wand_info_offset2`**: Another offset value for UI elements related to wand information.

```xml
<Language
	name="Deutsche"
	font_default="data/fonts/font_pixel.xml"
	font_inventory_title="data/fonts/font_pixel_big.xml"
	font_important_message_title="data/fonts/font_pixel_huge.xml"
	font_world_space_message="data/fonts/font_pixel.xml"
	fonts_utf8="1"
	fonts_pixel_font="1"
	ui_action_info_offset2="35"
	ui_wand_info_offset1="15"
	ui_wand_info_offset2="30"
>
</Language>
```