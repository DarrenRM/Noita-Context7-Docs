---
title: Small Numbers Font Definition
category: fonts
---

# Small Numbers Font Definition

This document describes the `font_small_numbers.xml` file, which defines a small font used for displaying numbers and specific characters in Noita.

## Font Properties

These global properties define the overall characteristics of the font.

| Property     | Description                                     | Value |
|--------------|-------------------------------------------------|-------|
| `Texture`    | Path to the texture file containing the glyphs. | `data/fonts/font_small_numbers.png` |
| `LineHeight` | The vertical spacing between lines of text.     | `7`   |
| `CharSpace`  | Additional horizontal space between characters. | `0`   |
| `WordSpace`  | Additional horizontal space between words.      | `4`   |

## Character Definitions (`QuadChar`)

Each `QuadChar` element defines a single character's appearance and placement within the font texture.

### Key Attributes:

*   **`id`**: The Unicode or ASCII value of the character. This is crucial for mapping characters to their visual representation.
*   **`rect_x`**: The horizontal starting coordinate of the character's bounding box within the texture.
*   **`rect_y`**: The vertical starting coordinate of the character's bounding box within the texture.
*   **`rect_w`**: The width of the character's bounding box in the texture.
*   **`rect_h`**: The height of the character's bounding box in the texture.
*   **`width`**: The effective horizontal width of the character when rendered. This can differ from `rect_w` to allow for kerning or tighter spacing.
*   **`offset_x`, `offset_y`**: Used for fine-tuning the character's position.

### Character Table (Numbers and Common Symbols)

| ID   | Character | `rect_x` | `rect_y` | `rect_w` | `rect_h` | `width` | Notes                               |
|------|-----------|----------|----------|----------|----------|---------|-------------------------------------|
| `48` | `0`       | `0`      | `0`      | `4`      | `6`      | `4`     | Digit Zero                          |
| `49` | `1`       | `5`      | `0`      | `4`      | `6`      | `4`     | Digit One                           |
| `50` | `2`       | `10`     | `0`      | `4`      | `6`      | `4`     | Digit Two                           |
| `51` | `3`       | `15`     | `0`      | `4`      | `6`      | `4`     | Digit Three                         |
| `52` | `4`       | `20`     | `0`      | `4`      | `6`      | `4`     | Digit Four                          |
| `53` | `5`       | `25`     | `0`      | `4`      | `6`      | `4`     | Digit Five                          |
| `54` | `6`       | `30`     | `0`      | `4`      | `6`      | `4`     | Digit Six                           |
| `55` | `7`       | `35`     | `0`      | `4`      | `6`      | `4`     | Digit Seven                         |
| `56` | `8`       | `40`     | `0`      | `4`      | `6`      | `4`     | Digit Eight                         |
| `57` | `9`       | `45`     | `0`      | `4`      | `6`      | `4`     | Digit Nine                          |
| `8734`| `∞`      | `50`     | `0`      | `9`      | `6`      | `9`     | Infinity Symbol                     |
| `46` | `.`       | `158`    | `0`      | `2`      | `6`      | `2`     | Period/Decimal Point                |

### Character Table (Other Symbols and Letters)

This section lists other defined characters, including some Greek letters and common symbols. Note that some IDs might appear to be duplicates but are defined with different glyphs or positions.

| ID   | Character | `rect_x` | `rect_y` | `rect_w` | `rect_h` | `width` | Notes                               |
|------|-----------|----------|----------|----------|----------|---------|-------------------------------------|
| `75` | `K`       | `61`     | `0`      | `6`      | `6`      | `6`     | Uppercase K                         |
| `77` | `M`       | `68`     | `0`      | `6`      | `6`      | `6`     | Uppercase M                         |
| `1051`| `Σ`      | `74`     | `0`      | `6`      | `6`      | `6`     | Uppercase Sigma (Greek)             |
| `1053`| `Ω`      | `80`     | `0`      | `6`      | `6`      | `6`     | Uppercase Omega (Greek)             |
| `109` | `m`       | `86`     | `0`      | `6`      | `6`      | `6`     | Lowercase m                         |
| `105` | `i`       | `92`     | `0`      | `2`      | `6`      | `2`     | Lowercase i                         |
| `108` | `l`       | `95`     | `0`      | `2`      | `6`      | `2`     | Lowercase l                         |
| `110` | `n`       | `98`     | `0`      | `4`      | `6`      | `4`     | Lowercase n                         |
| `111` | `o`       | `104`    | `0`      | `4`      | `6`      | `4`     | Lowercase o                         |
| `84`  | `T`       | `110`    | `0`      | `5`      | `6`      | `5`     | Uppercase T                         |
| `115` | `s`       | `116`    | `0`      | `3`      | `6`      | `3`     | Lowercase s                         |
| `100` | `d`       | `122`    | `0`      | `4`      | `6`      | `4`     | Lowercase d                         |
| `107` | `k`       | `128`    | `0`      | `4`      | `6`      | `4`     | Lowercase k                         |
| `116` | `t`       | `134`    | `0`      | `4`      | `6`      | `4`     | Lowercase t                         |
| `121` | `y`       | `140`    | `0`      | `4`      | `6`      | `4`     | Lowercase y                         |
| `1067`| `Σ`      | `146`    | `0`      | `6`      | `6`      | `6`     | Uppercase Sigma (Greek) - Duplicate?|
| `1057`| `Ψ`      | `152`    | `0`      | `6`      | `6`      | `6`     | Uppercase Psi (Greek)               |

### Notes on Duplicate/Overlapping Definitions:

Some character IDs (e.g., `1052`, `1084`, `1083`, `1085`, `1099`, `1089`) are defined multiple times or with overlapping `rect_x` values. This can indicate:
*   **Alternative Glyphs**: Different visual representations for the same character ID. The game likely uses the last definition encountered.
*   **Character Variants**: Potentially for different languages or contexts, though less common for a "small numbers" font.
*   **Legacy/Unused Definitions**: Entries that are no longer used or are remnants of previous versions.

For modding purposes, it's essential to check the actual rendered output or the game's internal logic to determine which definition is active if multiple exist for the same ID.

```xml
<FontData>
  <Texture>
    data/fonts/font_small_numbers.png
  </Texture>
  <LineHeight>
    7
  </LineHeight>
  <CharSpace>
    0
  </CharSpace>
  <WordSpace>
    4
  </WordSpace>
  <QuadChar id="48" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="0" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="49" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="5" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="50" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="10" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="51" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="15" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="52" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="20" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="53" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="25" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="54" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="30" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="55" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="35" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="56" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="40" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="57" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="45" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="8734" offset_x="0" offset_y="0" rect_h="6" rect_w="9" rect_x="50" rect_y="0" width="9" >
  </QuadChar>
  
  <QuadChar id="75" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="61" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="77" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="68" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1051" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="74" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1053" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="80" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="109" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="86" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="105" offset_x="0" offset_y="0" rect_h="6" rect_w="2" rect_x="92" rect_y="0" width="2" >
  </QuadChar>
  <QuadChar id="108" offset_x="0" offset_y="0" rect_h="6" rect_w="2" rect_x="95" rect_y="0" width="2" >
  </QuadChar>
  <QuadChar id="110" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="98" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="111" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="104" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="84" offset_x="0" offset_y="0" rect_h="6" rect_w="5" rect_x="110" rect_y="0" width="5" >
  </QuadChar>
  <QuadChar id="115" offset_x="0" offset_y="0" rect_h="6" rect_w="3" rect_x="116" rect_y="0" width="3" >
  </QuadChar>
  <QuadChar id="100" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="122" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="107" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="128" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="116" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="134" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="121" offset_x="0" offset_y="0" rect_h="6" rect_w="4" rect_x="140" rect_y="0" width="4" >
  </QuadChar>
  <QuadChar id="1067" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="146" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1057" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="152" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="46" offset_x="0" offset_y="0" rect_h="6" rect_w="2" rect_x="158" rect_y="0" width="2" >
  </QuadChar>
  
  <QuadChar id="1052" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="68" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1084" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="68" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1083" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="74" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1085" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="80" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1099" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="146" rect_y="0" width="6" >
  </QuadChar>
  <QuadChar id="1089" offset_x="0" offset_y="0" rect_h="6" rect_w="6" rect_x="152" rect_y="0" width="6" >
  </QuadChar>
</FontData>
```