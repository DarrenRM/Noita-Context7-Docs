---
title: Pixel White Font Definition
category: fonts
---

# Pixel White Font Definition

This document describes the configuration for the `font_pixel_white.xml` file, which defines a pixelated white font used in Noita.

## Font Properties

The main `<FontData>` element contains attributes that define the overall characteristics of the font.

### Key Attributes

*   `color_r`, `color_g`, `color_b`, `color_a`: These attributes define the RGBA color of the font. In this case, `1, 1, 1, 1` means a fully opaque white color.

### Texture

*   `<Texture>`: Specifies the image file containing the font's glyphs.
    *   `data/fonts/font_pixel.png`: The path to the texture atlas for this font.

### Spacing and Height

*   `<LineHeight>`: The vertical space between lines of text.
    *   `7`: Each line will occupy 7 pixels vertically.
*   `<CharSpace>`: The default horizontal space between characters.
    *   `0`: No extra space is added between characters by default.
*   `<WordSpace>`: The horizontal space added between words.
    *   `6`: Words will be separated by 6 pixels.

## Character Definitions (`<QuadChar>`)

Each `<QuadChar>` element defines a single character's properties within the font texture.

### Key Attributes

*   `id`: The Unicode (decimal) identifier for the character.
*   `rect_x`, `rect_y`: The top-left coordinates of the character's bounding box within the texture.
*   `rect_w`, `rect_h`: The width and height of the character's bounding box within the texture.
*   `width`: The effective horizontal width of the character for rendering and spacing purposes.
*   `offset_x`, `offset_y`: Additional offsets applied to the character's position. These are typically `0` for simple pixel fonts.

### Example Character Definitions

Here's a sample of the character definitions, illustrating the structure:

| ID  | Character | `rect_x` | `rect_y` | `rect_w` | `rect_h` | `width` |
| :-- | :-------- | :------- | :------- | :------- | :------- | :------ |
| 32  | (space)   | 0        | 0        | 3        | 11       | 3       |
| 33  | !         | 4        | 0        | 3        | 11       | 3       |
| 34  | "         | 8        | 0        | 4        | 11       | 4       |
| 35  | #         | 13       | 0        | 6        | 11       | 6       |
| 48  | 0         | 93       | 0        | 6        | 11       | 6       |
| 49  | 1         | 100      | 0        | 4        | 11       | 4       |
| 65  | A         | 202      | 0        | 6        | 11       | 6       |
| 97  | a         | 420      | 0        | 4        | 11       | 4       |
| 122 | z         | 545      | 0        | 4        | 11       | 4       |
| 8734| ∞         | 1472     | 0        | 10       | 11       | 10      |

*(Note: The table above shows a selection of characters. The full file defines many more characters, including extended Latin and Cyrillic alphabets.)*

This XML file is crucial for defining how text is rendered in the game, controlling its appearance, spacing, and the specific glyphs used. Modifying this file can change the font's color, spacing, or even allow for custom character mappings if the texture is also updated.