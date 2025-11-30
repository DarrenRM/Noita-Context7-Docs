---
title: Giant Spatial Data
category: entities/enemies_gfx
---

---

# Giant Spatial Data

This file defines the spatial data for the Giant enemy in Noita, specifically its graphical components and their associated colors. This data is crucial for understanding how the enemy is rendered and how its different parts are visually distinguished.

## Key Components and Colors

The following table outlines the primary graphical components of the Giant and their corresponding color codes. These colors are likely used to differentiate body parts or for specific rendering effects.

| Component   | Color (RGBA) |
| :---------- | :----------- |
| `left_foot` | `ffff0000`   |
| `right_foot`| `ff800000`   |
| `left_hand` | `ffff00ff`   |
| `right_hand`| `ff0000ff`   |
| `head`      | `ffffff00`   |
| `center`    | `ff00ff00`   |

## Color Format

The color codes are represented in RGBA (Red, Green, Blue, Alpha) format, where each component is a two-digit hexadecimal number.

*   **FF**: Indicates full opacity (Alpha).
*   **Hexadecimal values (00-FF)**: Represent the intensity of Red, Green, and Blue, respectively.

For example, `ffff0000` translates to:
*   Red: `ff` (maximum)
*   Green: `ff` (maximum)
*   Blue: `00` (minimum)
*   Alpha: `00` (minimum - this seems to be a typo in the source, likely intended to be `ff` for opacity. If `00` is indeed the intended alpha, the component would be invisible.)

**Note:** The alpha channel in the provided `center` component (`ff00ff00`) appears to be `ff`, indicating full opacity. However, the `head` component (`ffffff00`) has an alpha of `00`, which would make it invisible. This might be an error in the original data or intended for a specific rendering effect.

## AI Modding Considerations

When modding the Giant enemy, understanding these spatial data points can be useful for:

*   **Customizing Visuals:** Modifying these color values can change the appearance of the Giant.
*   **Targeting Specific Parts:** If your mod interacts with specific body parts (e.g., for damage or status effects), knowing their identifiers is essential.
*   **Animation and Effects:** These components might be referenced in animation or particle effect definitions.