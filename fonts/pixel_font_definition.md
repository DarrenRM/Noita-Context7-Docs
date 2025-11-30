---
title: Pixel Font Definition
category: fonts
---

# Pixel Font Definition

This document describes the configuration for the pixel font used in Noita. It defines the texture containing the font glyphs and the spacing parameters for rendering text.

## Core Font Properties

These are the main settings that control the overall appearance and spacing of the font.

*   **`<Texture>`**: Specifies the image file that contains all the font glyphs.
    *   `data/fonts/font_pixel.png`: The path to the texture file.
*   **`<LineHeight>`**: The vertical space between lines of text.
    *   `7`: Each line will have a height of 7 pixels.
*   **`<CharSpace>`**: The default horizontal space between individual characters.
    *   `0`: No extra space is added between characters by default.
*   **`<WordSpace>`**: The horizontal space added between words.
    *   `6`: Words will be separated by 6 pixels.

## Character Definitions (`<QuadChar>`)

Each `<QuadChar>` element defines a specific character and its properties within the font texture.

*   **`id`**: The Unicode (or ASCII) code of the character.
*   **`rect_x`**: The x-coordinate of the top-left corner of the character's bounding box within the texture.
*   **`rect_y`**: The y-coordinate of the top-left corner of the character's bounding box within the texture.
*   **`rect_w`**: The width of the character's bounding box in the texture.
*   **`rect_h`**: The height of the character's bounding box in the texture.
*   **`width`**: The effective horizontal width of the character when rendered. This determines how much space the character occupies on a line.
*   **`offset_x`**, **`offset_y`**: These attributes are present but appear to be unused or set to 0 for this font, indicating no additional horizontal or vertical offset for the glyph.

### Key Character Examples:

| ID  | Character | `rect_x` | `rect_w` | `width` | Description                               |
| :-- | :-------- | :------- | :------- | :------ | :---------------------------------------- |
| 32  | (space)   | 0        | 3        | 3       | Space character                           |
| 33  | !         | 4        | 3        | 3       | Exclamation mark                          |
| 48  | 0         | 93       | 6        | 6       | Digit zero                                |
| 65  | A         | 202      | 6        | 6       | Uppercase 'A'                             |
| 97  | a         | 420      | 4        | 4       | Lowercase 'a'                             |
| 120 | x         | 535      | 4        | 4       | Lowercase 'x'                             |
| 8734| ∞         | 1472     | 10       | 10      | Infinity symbol                           |

**Note:** The `rect_x` values are cumulative, indicating the horizontal position of each character's glyph within the `font_pixel.png` texture. The `width` attribute is crucial for determining the spacing and layout of text.

---