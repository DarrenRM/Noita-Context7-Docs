---
title: Sheep Ragdoll Sprite Definitions
category: ragdolls
---

---

# Sheep Ragdoll Sprite Definitions

This documentation outlines the sprite definitions for the "sheep" ragdoll entity in Noita, as found in `data/ragdolls/sheep/filenames.txt`. These files specify the individual image assets that constitute the sheep's ragdoll.

## Sprite Components

The sheep ragdoll is composed of several distinct sprite parts, each corresponding to a specific body segment. These are defined by their file paths.

### Key Sprite Files

*   `data/ragdolls/sheep/head.png`: The sprite for the sheep's head.
*   `data/ragdolls/sheep/right_torso.png`: The sprite for the right side of the sheep's torso.
*   `data/ragdolls/sheep/left_torso.png`: The sprite for the left side of the sheep's torso.
*   `data/ragdolls/sheep/left_frontleg.png`: The sprite for the sheep's left front leg.
*   `data/ragdolls/sheep/right_frontleg.png`: The sprite for the sheep's right front leg.
*   `data/ragdolls/sheep/left_hindleg.png`: The sprite for the sheep's left hind leg.
*   `data/ragdolls/sheep/right_hindleg.png`: The sprite for the sheep's right hind leg.

## Usage in Modding

When creating or modifying ragdoll entities, understanding these sprite definitions is crucial for:

*   **Visual Customization:** Replacing or altering these `.png` files allows for visual changes to the sheep ragdoll.
*   **Animation:** The arrangement and interaction of these sprites contribute to the ragdoll's animation and physics.
*   **Entity Creation:** If creating a new entity that utilizes a ragdoll, you would reference similar sprite definitions for its various parts.

This file serves as a direct mapping from the entity's ragdoll structure to its visual assets.