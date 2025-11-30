---
title: Terminal Font Definition
category: fonts
---

# Terminal Font Definition

This document describes the configuration for the terminal font used in Noita. It defines the texture containing the font glyphs and the spacing parameters for rendering text.

## Font Texture and Spacing

### Texture

The font glyphs are stored in a single texture file.

*   **`<Texture>`**: Specifies the path to the font texture image.
    *   `data/fonts/terminal_font.png`

### Spacing Parameters

These attributes control how characters and words are spaced when rendered.

*   **`<LineHeight>`**: The vertical distance between lines of text.
    *   `20`
*   **`<CharSpace>`**: The horizontal space between individual characters.
    *   `1`
*   **`<WordSpace>`**: The horizontal space between words.
    *   `0`

## Character Definitions

Each `<Char>` element defines a single glyph within the font texture. The `id` attribute corresponds to the ASCII or Unicode value of the character. The `rect_` attributes define the bounding box of the character within the texture.

*   **`id`**: The numerical identifier for the character (e.g., ASCII value).
*   **`rect_h`**: The height of the character's bounding box in pixels.
*   **`rect_w`**: The width of the character's bounding box in pixels.
*   **`rect_x`**: The x-coordinate of the top-left corner of the character's bounding box within the texture.
*   **`rect_y`**: The y-coordinate of the top-left corner of the character's bounding box within the texture.

### Key Character Definitions (Sample)

The following table provides a sample of character definitions. The full file contains definitions for a wide range of characters, including numbers, uppercase and lowercase letters, and various symbols.

| ID  | Character | `rect_h` | `rect_w` | `rect_x` | `rect_y` |
| :-- | :-------- | :------- | :------- | :------- | :------- |
| 32  | Space     | 16       | 8        | 188      | 0        |
| 48  | 0         | 16       | 8        | 260      | 0        |
| 49  | 1         | 16       | 8        | 260      | 16       |
| 65  | A         | 16       | 8        | 332      | 16       |
| 97  | a         | 16       | 8        | 476      | 16       |
| 115 | s         | 16       | 8        | 476      | 160      |
| 120 | x         | 16       | 8        | 548      | 128      |

**Note:** The `rect_x` and `rect_y` values are crucial for correctly mapping each character to its visual representation in the `terminal_font.png` texture. Modifying these values will alter the appearance or position of characters.

```xml
<FontData>
  <Texture>
    data/fonts/terminal_font.png
  </Texture>
  <LineHeight>
    20
  </LineHeight>
  <CharSpace>
    1
  </CharSpace>
  <WordSpace>
    0
  </WordSpace>
  <!-- ... other character definitions ... -->
  <Char id="32" rect_h="16" rect_w="8" rect_x="188" rect_y="0" >
  </Char>
  <Char id="48" rect_h="16" rect_w="8" rect_x="260" rect_y="0" >
  </Char>
  <Char id="49" rect_h="16" rect_w="8" rect_x="260" rect_y="16" >
  </Char>
  <Char id="65" rect_h="16" rect_w="8" rect_x="332" rect_y="16" >
  </Char>
  <Char id="97" rect_h="16" rect_w="8" rect_x="476" rect_y="16" >
  </Char>
  <Char id="115" rect_h="16" rect_w="8" rect_x="476" rect_y="160" >
  </Char>
  <Char id="120" rect_h="16" rect_w="8" rect_x="548" rect_y="128" >
  </Char>
  <!-- ... other character definitions ... -->
</FontData>
```