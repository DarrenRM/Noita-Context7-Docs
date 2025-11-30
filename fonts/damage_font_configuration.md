---
title: Damage Font Configuration
category: fonts
---

# Damage Font Configuration

This document details the configuration for the damage font used in Noita, defining its visual properties and character mappings.

## Core Font Properties

These attributes define the overall layout and spacing of the font.

*   **`<Texture>`**: Specifies the image file containing the font's glyphs.
    *   `data/fonts/font_damage.png`: The texture file for this font.
*   **`<LineHeight>`**: The vertical spacing between lines of text.
    *   `6`: Sets the line height to 6 pixels.
*   **`<CharSpace>`**: The horizontal space between individual characters.
    *   `0`: No additional space is added between characters.
*   **`<WordSpace>`**: The horizontal space added between words.
    *   `5`: Sets the word spacing to 5 pixels.

## Character Definitions (`<QuadChar>`)

Each `<QuadChar>` element defines a specific character's appearance and position within the font texture. The `id` attribute corresponds to the ASCII value of the character.

Key attributes for `<QuadChar>`:

*   **`id`**: The ASCII code of the character being defined.
*   **`rect_x`**: The x-coordinate of the character's bounding box in the texture.
*   **`rect_y`**: The y-coordinate of the character's bounding box in the texture.
*   **`rect_w`**: The width of the character's bounding box in the texture.
*   **`rect_h`**: The height of the character's bounding box in the texture.
*   **`width`**: The effective width of the character for rendering purposes (can differ from `rect_w` for kerning or spacing adjustments).
*   **`offset_x`**: Horizontal offset for the character's rendering.
*   **`offset_y`**: Vertical offset for the character's rendering.

### Example Character Mappings

The following table shows a sample of character definitions from this font file.

| ID | Character | `rect_x` | `rect_y` | `rect_w` | `rect_h` | `width` | `offset_x` | `offset_y` |
| :-- | :-------- | :------- | :------- | :------- | :------- | :------ | :--------- | :--------- |
| 45 | -         | 0        | 0        | 5        | 6        | 5       | 0          | 0          |
| 48 | 0         | 6        | 0        | 5        | 6        | 5       | 0          | 0          |
| 49 | 1         | 12       | 0        | 4        | 6        | 4       | 0          | 0          |
| 50 | 2         | 17       | 0        | 5        | 6        | 5       | 0          | 0          |
| 51 | 3         | 23       | 0        | 5        | 6        | 5       | 0          | 0          |
| 52 | 4         | 29       | 0        | 5        | 6        | 5       | 0          | 0          |
| 53 | 5         | 35       | 0        | 5        | 6        | 5       | 0          | 0          |
| 54 | 6         | 41       | 0        | 5        | 6        | 5       | 0          | 0          |
| 55 | 7         | 47       | 0        | 5        | 6        | 5       | 0          | 0          |
| 56 | 8         | 53       | 0        | 5        | 6        | 5       | 0          | 0          |
| 57 | 9         | 59       | 0        | 5        | 6        | 5       | 0          | 0          |

*(Note: The full file contains definitions for many more characters, including uppercase and lowercase letters, punctuation, and symbols. This table provides a representative sample.)*