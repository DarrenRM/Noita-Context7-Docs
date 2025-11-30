---
title: Player Spatial Data
category: entities/gfx
---

# Player Spatial Data

This file defines the spatial data for the player's visual components, mapping specific colors to different body parts. This is crucial for visual effects and potentially for certain gameplay mechanics that interact with specific player body parts.

## Key Color Mappings

The following table outlines the primary color mappings and their corresponding player body parts. The format is `RGBA` where `R`, `G`, `B`, and `A` represent Red, Green, Blue, and Alpha values respectively, ranging from 00 to ff.

| Color (RGBA) | Body Part   |
| :----------- | :---------- |
| `ffff0000`   | `left_foot` |
| `ff800000`   | `right_foot`|
| `ffff00ff`   | `left_hand` |
| `ff0000ff`   | `right_hand`|
| `ffffff00`   | `head`      |
| `ff00ff00`   | `center`    |

## Usage in Modding

This data is primarily used by the game engine to identify and manipulate specific parts of the player's sprite. Modders can leverage this information for:

*   **Custom Visual Effects:** Applying particle effects or shaders to specific body parts (e.g., making only the feet glow).
*   **Targeted Interactions:** Developing mods that interact with or modify specific player limbs or the player's core.
*   **Animation Tweaks:** Understanding how different parts are defined can be helpful when creating custom animations or modifying existing ones.

## Technical Details

The color values are represented in hexadecimal. Each pair of characters (`ff`, `00`, `80`) corresponds to an 8-bit value for Red, Green, Blue, and Alpha channels.

*   `ff` indicates full intensity (255).
*   `00` indicates no intensity (0).
*   `80` indicates half intensity (128).

The `center` mapping is often used as a general reference point for the player's origin or core.