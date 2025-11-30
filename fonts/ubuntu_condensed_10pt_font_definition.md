---
title: Ubuntu Condensed 10pt Font Definition
category: fonts
---

# Ubuntu Condensed 10pt Font Definition

This document describes the configuration for the "Ubuntu Condensed" font at a 10-point size used within Noita. It defines the texture atlas and the specific metrics for each character.

## Core Font Properties

These are the fundamental settings that define the font's overall appearance and spacing.

*   **Texture**: `data/fonts/ubuntu_condensed_10.png`
    *   This specifies the image file containing all the glyphs for this font.
*   **LineHeight**: `11`
    *   The vertical distance between baselines of consecutive lines of text.
*   **CharSpace**: `0`
    *   The default horizontal space added between characters.
*   **WordSpace**: `0`
    *   The default horizontal space added between words.

## Character Metrics (`QuadChar`)

Each `QuadChar` element defines the properties of a single character (glyph) within the font texture. The key attributes are:

*   **id**: The ASCII (or Unicode) code of the character.
*   **rect\_x**, **rect\_y**: The top-left coordinates of the character's bounding box within the texture atlas.
*   **rect\_w**, **rect\_h**: The width and height of the character's bounding box within the texture atlas.
*   **offset\_x**, **offset\_y**: Adjustments to the character's position relative to its baseline.
*   **width**: The horizontal advance width of the character, determining how much space it occupies on a line.

### Character Data Summary

The following table provides a sample of the character metrics. The full list defines every character from ASCII 32 (space) to 127 (DEL).

| ID  | Char | rect\_x | rect\_y | rect\_w | rect\_h | offset\_x | offset\_y | width   |
| :-- | :--- | :------ | :------ | :------ | :------ | :-------- | :-------- | :------ |
| 32  |      | 1       | 1       | 0       | 0       | 0         | 0         | 2.60928 |
| 33  | !    | 3       | 1       | 3       | 11      | 0         | -10       | 3.51918 |
| 34  | "    | 8       | 1       | 5       | 5       | 0         | -11       | 5.05798 |
| 35  | #    | 15      | 1       | 7       | 10      | 0         | -10       | 7.58698 |
| 36  | $    | 24      | 1       | 6       | 13      | 0         | -11       | 5.75379 |
| 37  | %    | 32      | 1       | 8       | 11      | 0         | -10       | 8.63069 |
| 48  | 0    | 103     | 1       | 6       | 11      | 0         | -10       | 5.75379 |
| 65  | A    | 109     | 17      | 7       | 10      | 0         | -10       | 6.7306  |
| 97  | a    | 117     | 47      | 5       | 9       | 0         | -8        | 5.80731 |
| 100 | d    | 15      | 63      | 6       | 12      | 0         | -11       | 6.24889 |
| 122 | z    | 50      | 78      | 5       | 8       | 0         | -8        | 4.7636  |

---