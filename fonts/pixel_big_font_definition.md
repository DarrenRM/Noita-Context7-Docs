---
title: Pixel Big Font Definition
category: fonts
---

# Pixel Big Font Definition

This document describes the configuration for the "font_pixel_big" font used in Noita. It defines the texture containing the font glyphs and the spacing parameters for rendering text.

## Key Attributes

### Texture
Specifies the image file that contains all the characters for this font.

*   **Path**: `data/fonts/font_pixel_big.png`

### Spacing Parameters

These attributes control the visual spacing of text rendered with this font.

*   **LineHeight**: The vertical space between lines of text.
    *   Value: `7`
*   **CharSpace**: Additional horizontal space added between individual characters.
    *   Value: `0`
*   **WordSpace**: Additional horizontal space added between words.
    *   Value: `6`

## Character Definitions (`QuadChar`)

Each `QuadChar` element defines a single character's properties within the font texture. The most important attributes are:

*   **id**: The Unicode (decimal) identifier for the character.
*   **width**: The horizontal width of the character glyph.
*   **rect_x**: The horizontal starting position of the character's bounding box within the texture.
*   **rect_y**: The vertical starting position of the character's bounding box within the texture.
*   **rect_w**: The width of the character's bounding box within the texture.
*   **rect_h**: The height of the character's bounding box within the texture.

### Character Table (Sample)

This table shows a sample of character definitions. The full file contains definitions for a wide range of ASCII and extended characters.

| ID  | Character | Width | Rect X | Rect Y | Rect W | Rect H |
| :-- | :-------- | :---- | :----- | :----- | :----- | :----- |
| 32  | (space)   | 3     | 0      | 0      | 3      | 11     |
| 33  | !         | 3     | 4      | 0      | 3      | 11     |
| 34  | "         | 4     | 8      | 0      | 4      | 11     |
| 35  | #         | 6     | 13     | 0      | 6      | 11     |
| 48  | 0         | 6     | 93     | 0      | 6      | 11     |
| 65  | A         | 6     | 212    | 0      | 6      | 11     |
| 97  | a         | 6     | 431    | 0      | 6      | 11     |
| 122 | z         | 6     | 605    | 0      | 6      | 11     |
| 192 | À         | 6     | 665    | 0      | 6      | 11     |
| 1040| А (Cyrillic)| 6     | 1141   | 0      | 6      | 11     |
| 8211| – (En dash)| 6     | 1594   | 0      | 6      | 11     |

**Note:** The `offset_x` and `offset_y` attributes are consistently `0` for all characters in this font definition, indicating no additional offset is applied to the character's position beyond its defined rectangle.