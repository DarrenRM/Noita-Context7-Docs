---
title: Japanese Language Configuration
category: translations
---

```

# Japanese Language Configuration

This file configures the Japanese language settings for Noita, primarily focusing on font usage and UI text offsets.

## Key Attributes

*   **`name`**: Specifies the language name, "日本語" (Japanese).
*   **`font_default`**: Sets the default font for general game text.
*   **`font_inventory_title`**: Defines the font used for inventory titles.
*   **`font_important_message_title`**: Sets the font for important message titles.
*   **`font_world_space_message`**: Specifies the font for messages displayed in the game world.
*   **`fonts_utf8`**: Indicates that UTF-8 encoding is used for fonts (set to "1" for enabled).
*   **`ui_action_info_offset2`**: Adjusts the vertical offset for action information UI elements.
*   **`ui_wand_info_offset1`**: Adjusts the vertical offset for wand information UI elements.
*   **`ui_wand_info_offset2`**: Further adjusts the vertical offset for wand information UI elements.

## Example Usage

This configuration ensures that Japanese characters are displayed correctly and that UI elements are positioned appropriately for the Japanese language. Modders can reference these settings to ensure their custom text or UI elements integrate seamlessly with the Japanese localization.

```xml
<Language
	name="日本語"
	font_default="data/fonts/generated/notosans_jp_48.bin"
	font_inventory_title="data/fonts/generated/notosans_jp_48.bin"
	font_important_message_title="data/fonts/generated/notosans_jp_48.bin"
	font_world_space_message="data/fonts/generated/notosans_jp_48.bin"
	fonts_utf8="1"
	ui_action_info_offset2="35"
	ui_wand_info_offset1="0"
	ui_wand_info_offset2="20"
>
</Language>