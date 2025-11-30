---
title: Pixel Huge Font Definition
category: fonts/
---

# Pixel Huge Font Definition

This document describes the configuration for the "Pixel Huge" font used in Noita. It defines the texture containing the font glyphs and the spacing parameters for rendering text.

## Core Font Properties

These are the primary settings that govern how the font is rendered.

*   **Texture**: `data/fonts/font_pixel_huge.png`
    *   The image file containing all the glyphs for this font.
*   **LineHeight**: `7`
    *   The vertical space allocated for each line of text.
*   **CharSpace**: `0`
    *   The default horizontal space between individual characters.
*   **WordSpace**: `6`
    *   The additional horizontal space added between words.

## Character Definitions (`QuadChar`)

Each `QuadChar` element defines a specific character and its properties within the texture. The `id` attribute corresponds to the ASCII or Unicode value of the character.

Key attributes for `QuadChar`:

*   **id**: The numerical identifier for the character (e.g., 32 for space, 65 for 'A').
*   **rect_x**: The x-coordinate of the top-left corner of the character's bounding box within the texture.
*   **rect_y**: The y-coordinate of the top-left corner of the character's bounding box within the texture.
*   **rect_w**: The width of the character's bounding box within the texture.
*   **rect_h**: The height of the character's bounding box within the texture.
*   **width**: The effective width of the character when rendered, including any padding.

### Example Character Definitions:

| id   | Character | rect_x | rect_y | rect_w | rect_h | width |
| :--- | :-------- | :----- | :----- | :----- | :----- | :---- |
| 32   | (space)   | 0      | 0      | 8      | 15     | 8     |
| 33   | !         | 9      | 0      | 4      | 15     | 4     |
| 46   | .         | 110    | 0      | 4      | 15     | 4     |
| 48   | 0         | 124    | 0      | 8      | 15     | 8     |
| 65   | A         | 277    | 0      | 8      | 15     | 8     |
| 97   | a         | 557    | 0      | 8      | 15     | 8     |
| 101  | e         | 593    | 0      | 8      | 15     | 8     |
| 122  | z         | 779    | 0      | 8      | 15     | 8     |
| 1072 | р (Cyrillic) | 1742 | 0      | 8      | 15     | 8     |
| 8734 | ∞         | 2084   | 0      | 10     | 15     | 10    |

*(Note: The table above shows a selection of characters. The full file defines many more characters, including various punctuation, numbers, uppercase and lowercase letters, and extended Latin/Cyrillic characters.)*

This font definition is crucial for any mod that needs to display custom text or modify existing in-game text. By understanding these parameters, you can ensure your text renders correctly and with the desired spacing.