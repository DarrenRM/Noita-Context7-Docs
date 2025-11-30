---
title: Ubuntu Condensed 18 Font Definition
category: fonts
---

# Ubuntu Condensed 18 Font Definition

This document describes the configuration for the "Ubuntu Condensed 18" font used in Noita. It defines the texture containing the glyphs and the specific metrics for each character.

## Font Metrics

These global settings define the spacing and line height for the font.

*   **LineHeight**: The vertical distance between lines of text.
    *   Value: `20`
*   **CharSpace**: Additional horizontal space added between characters.
    *   Value: `0`
*   **WordSpace**: Additional horizontal space added between words.
    *   Value: `0`

## Character Definitions (`QuadChar`)

Each `QuadChar` element defines the properties of a single character glyph. The key attributes are:

*   **id**: The ASCII (or Unicode) code for the character.
*   **width**: The horizontal advance width of the character. This is the distance the cursor moves after printing the character.
*   **offset\_x**: Horizontal offset of the glyph's bounding box from its origin.
*   **offset\_y**: Vertical offset of the glyph's bounding box from its origin.
*   **rect\_x**: The x-coordinate of the top-left corner of the glyph's bounding box within the texture.
*   **rect\_y**: The y-coordinate of the top-left corner of the glyph's bounding box within the texture.
*   **rect\_w**: The width of the glyph's bounding box within the texture.
*   **rect\_h**: The height of the glyph's bounding box within the texture.

### Key Character Definitions

The following table highlights some common characters and their definitions. The full list of characters is extensive and can be found in the raw XML data.

| ID  | Character | Width   | Offset X | Offset Y | Rect X | Rect Y | Rect W | Rect H |
| :-- | :-------- | :------ | :------- | :------- | :----- | :----- | :----- | :----- |
| 32  | Space     | 3.13113 | 0        | 0        | 1      | 1      | 0      | 0      |
| 46  | .         | 3.72525 | 0        | -2       | 101    | 1      | 3      | 3      |
| 48  | 0         | 6.90455 | 0        | -12      | 114    | 1      | 7      | 13     |
| 65  | A         | 8.07672 | 0        | -12      | 15     | 35     | 8      | 12     |
| 97  | a         | 6.96878 | 0        | -9       | 64     | 69     | 6      | 10     |
| 115 | s         | 5.47547 | 0        | -9       | 85     | 87     | 6      | 10     |
| 120 | x         | 6.29438 | 0        | -9       | 1      | 105    | 7      | 9      |

**Note:** The `rect_w` and `rect_h` for the space character (ID 32) are 0, indicating it's an empty glyph. The `width` attribute still defines its spacing.

### Full Character Table (Excerpt)

| ID  | Character | Width   | Offset X | Offset Y | Rect X | Rect Y | Rect W | Rect H |
| :-- | :-------- | :------ | :------- | :------- | :----- | :----- | :----- | :----- |
| 33  | !         | 4.22302 | 1        | -12      | 3      | 1      | 3      | 13     |
| 34  | "         | 6.06958 | 1        | -13      | 8      | 1      | 4      | 5      |
| 35  | #         | 9.10437 | 0        | -12      | 14     | 1      | 9      | 12     |
| 36  | $         | 6.90455 | 0        | -13      | 25     | 1      | 7      | 15     |
| 37  | %         | 10.3568 | 0        | -12      | 34     | 1      | 10     | 13     |
| 38  | &         | 8.20517 | 0        | -12      | 46     | 1      | 9      | 13     |
| 39  | '         | 3.56467 | 1        | -13      | 57     | 1      | 2      | 5      |
| 40  | (         | 4.57627 | 1        | -13      | 61     | 1      | 4      | 17     |
| 41  | )         | 4.57627 | 0        | -13      | 67     | 1      | 4      | 17     |
| 42  | *         | 6.21409 | 0        | -12      | 73     | 1      | 6      | 6      |
| 43  | +         | 6.90455 | 0        | -8       | 81     | 1      | 7      | 7      |
| 44  | ,         | 3.72525 | 0        | -2       | 90     | 1      | 3      | 5      |
| 45  | -         | 3.7413  | 0        | -6       | 95     | 1      | 4      | 2      |
| 47  | /         | 4.33541 | -1       | -13      | 106    | 1      | 6      | 16     |
| 49  | 1         | 6.90455 | 1        | -12      | 1      | 20     | 4      | 12     |
| 50  | 2         | 6.90455 | 0        | -12      | 7      | 20     | 6      | 12     |
| 51  | 3         | 6.90455 | 0        | -12      | 15     | 20     | 6      | 13     |
| 52  | 4         | 6.90455 | 0        | -12      | 23     | 20     | 7      | 12     |
| 53  | 5         | 6.90455 | 0        | -12      | 32     | 20     | 6      | 13     |
| 54  | 6         | 6.90455 | 1        | -12      | 40     | 20     | 6      | 13     |
| 55  | 7         | 6.90455 | 0        | -12      | 48     | 20     | 7      | 12     |
| 56  | 8         | 6.90455 | 0        | -12      | 57     | 20     | 7      | 13     |
| 57  | 9         | 6.90455 | 0        | -12      | 66     | 20     | 7      | 13     |
| 58  | :         | 3.72525 | 0        | -9       | 75     | 20     | 3      | 10     |
| 59  | ;         | 3.72525 | 0        | -9       | 80     | 20     | 3      | 12     |
| 60  | <         | 6.90455 | 0        | -9       | 85     | 20     | 7      | 8      |
| 61  | =         | 6.90455 | 0        | -7       | 94     | 20     | 7      | 5      |
| 62  | >         | 6.90455 | 0        | -9       | 103    | 20     | 7      | 8      |
| 63  | ?         | 5.49153 | 0        | -12      | 112    | 20     | 6      | 13     |
| 64  | @         | 13.231  | 1        | -12      | 1      | 35     | 12     | 15     |
| 66  | B         | 8.36575 | 1        | -12      | 25     | 35     | 7      | 13     |
| 67  | C         | 7.53078 | 0        | -12      | 34     | 35     | 8      | 13     |
| 68  | D         | 9.24889 | 1        | -12      | 44     | 35     | 8      | 13     |
| 69  | E         | 7.32203 | 1        | -12      | 54     | 35     | 6      | 12     |
| 70  | F         | 6.84032 | 1        | -12      | 62     | 35     | 6      | 12     |
| 71  | G         | 8.42997 | 0        | -12      | 70     | 35     | 8      | 13     |
| 72  | H         | 9.24889 | 1        | -12      | 80     | 35     | 7      | 12     |
| 73  | I         | 4.14273 | 1        | -12      | 89     | 35     | 2      | 12     |
| 74  | J         | 6.34255 | 0        | -12      | 93     | 35     | 6      | 13     |
| 75  | K         | 8.2694  | 1        | -12      | 101    | 35     | 8      | 12     |
| 76  | L         | 6.69581 | 1        | -12      | 111    | 35     | 6      | 12     |
| 77  | M         | 11.6574 | 1        | -12      | 1      | 52     | 10     | 12     |
| 78  | N         | 9.32917 | 1        | -12      | 13     | 52     | 7      | 12     |
| 79  | O         | 9.71454 | 0        | -12      | 22     | 52     | 9      | 13     |
| 80  | P         | 7.78769 | 1        | -12      | 33     | 52     | 7      | 12     |
| 81  | Q         | 9.71454 | 0        | -12      | 42     | 52     | 9      | 15     |
| 82  | R         | 8.25335 | 1        | -12      | 53     | 52     | 7      | 12     |
| 83  | S         | 6.42284 | 0        | -12      | 62     | 52     | 7      | 13     |
| 84  | T         | 6.84032 | 0        | -12      | 71     | 52     | 7      | 12     |
| 85  | U         | 8.81534 | 1        | -12      | 80     | 52     | 7      | 13     |
| 86  | V         | 7.98038 | 0        | -12      | 89     | 52     | 8      | 12     |
| 87  | W         | 12.1392 | 0        | -12      | 99     | 52     | 12     | 12     |
| 88  | X         | 7.56289 | 0        | -12      | 113    | 52     | 8      | 12     |
| 89  | Y         | 7.24175 | 0        | -12      | 1      | 69     | 8      | 12     |
| 90  | Z         | 6.93666 | 0        | -12      | 11     | 69     | 7      | 12     |
| 91  | [         | 4.51204 | 1        | -13      | 20     | 69     | 4      | 16     |
| 92  | \         | 4.33541 | -1       | -13      | 26     | 69     | 6      | 16     |
| 93  | ]         | 4.51204 | 0        | -13      | 34     | 69     | 4      | 16     |
| 94  | ^         | 6.90455 | 0        | -12      | 40     | 69     | 7      | 7      |
| 95  | _         | 5.89295 | -1       | 1        | 49     | 69     | 7      | 2      |
| 96  | `         | 5.04193 | 0        | -13      | 58     | 69     | 4      | 4      |
| 98  | b         | 7.49866 | 1        | -13      | 72     | 69     | 6      | 14     |
| 100 | d         | 7.49866 | 0        | -13      | 88     | 69     | 7      | 14     |
| 101 | e         | 7.00089 | 0        | -9       | 97     | 69     | 7      | 10     |
| 102 | f         | 4.91347 | 1        | -13      | 106    | 69     | 5      | 13     |
| 103 | g         | 7.49866 | 0        | -9       | 113    | 69     | 7      | 13     |
| 104 | h         | 7.73952 | 1        | -13      | 1      | 87     | 6      | 13     |
| 105 | i         | 3.88582 | 1        | -12      | 9      | 87     | 2      | 12     |
| 106 | j         | 3.88582 | -1       | -12      | 13     | 87     | 4      | 16     |
| 107 | k         | 6.85638 | 1        | -13      | 19     | 87     | 6      | 13     |
| 108 | l         | 3.90187 | 1        | -13      | 27     | 87     | 3      | 14     |
| 109 | m         | 11.2079 | 1        | -9       | 32     | 87     | 10     | 9      |
| 110 | n         | 7.73952 | 1        | -9       | 44     | 87     | 6      | 9      |
| 111 | o         | 7.43443 | 0        | -9       | 52     | 87     | 7      | 10     |
| 112 | p         | 7.49866 | 1        | -9       | 61     | 87     | 6      | 12     |
| 113 | q         | 7.49866 | 0        | -9       | 69     | 87     | 7      | 12     |
| 114 | r         | 5.26673 | 1        | -9       | 78     | 87     | 5      | 9      |
| 116 | t         | 5.15433 | 1        | -11      | 93     | 87     | 4      | 12     |
| 117 | u         | 7.7074  | 1        | -9       | 99     | 87     | 6      | 10     |
| 118 | v         | 6.37467 | 0        | -9       | 107    | 87     | 7      | 9      |
| 119 | w         | 9.20071 | 0        | -9       | 116    | 87     | 9      | 9      |
| 121 | y         | 6.35861 | 0        | -9       | 10     | 105    | 7      | 13     |
| 122 | z         | 5.71632 | 0        | -9       | 19     | 105    | 6      | 9      |
| 123 | {         | 4.27119 | 0        | -13      | 27     | 105    | 5      | 16     |
| 124 | |         | 4.31936 | 1        | -13      | 34     | 105    | 2      | 16     |
| 125 | }         | 4.27119 | 0        | -13      | 38     | 105    | 4      | 16     |
| 126 | ~         | 6.90455 | 0        | -7       | 44     | 105    | 7      | 4      |
| 127 | \x7f      | 8.02855 | 0        | -13      | 53     | 105    | 8      | 13     |