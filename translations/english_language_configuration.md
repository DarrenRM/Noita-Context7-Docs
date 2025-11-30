---
title: English Language Configuration
category: translations
---

# English Language Configuration

This document describes the configuration for the English language in Noita, focusing on font settings.

## Language Element

The `<Language>` element defines the primary language settings for the game.

### Key Attributes

*   **`name`**: Specifies the name of the language. For this file, it is "English".
*   **`font_default`**: The default font used for most in-game text.
*   **`font_inventory_title`**: The font used for titles within the inventory screen.
*   **`font_important_message_title`**: The font used for prominent, important message titles.
*   **`font_world_space_message`**: The font used for text displayed in the game world.
*   **`fonts_utf8`**: A flag indicating if UTF-8 character support is enabled for fonts (1 for enabled).
*   **`fonts_pixel_font`**: A flag indicating if pixel font rendering is enabled (1 for enabled).

---
```xml
<Language
	name="English"
	font_default="data/fonts/font_pixel.xml"
	font_inventory_title="data/fonts/font_pixel_big.xml"
	font_important_message_title="data/fonts/font_pixel_huge.xml"
	font_world_space_message="data/fonts/font_pixel.xml"
	fonts_utf8="1"
	fonts_pixel_font="1"
>
</Language>
```