---
title: Peasant Ragdoll Sprite Definitions
category: ragdolls
---

---

# Peasant Ragdoll Sprite Definitions

This documentation outlines the sprite definitions for the "peasant" ragdoll in Noita, as found in `data/ragdolls/peasant/filenames.txt`. These files specify the individual image assets used to construct the ragdoll's appearance when it is in a non-animated, physics-driven state.

## Key Sprite Components

The peasant ragdoll is composed of several distinct sprite parts, each corresponding to a specific body segment. These are defined by their file paths, typically located within the `data/ragdolls/peasant/` directory.

### Sprite Filenames

The following are the primary sprite files used for the peasant ragdoll:

*   `torso.png`: The main body sprite.
*   `right_thigh.png`: The upper part of the right leg.
*   `right_leg.png`: The lower part of the right leg.
*   `right_arm.png`: The upper part of the right arm.
*   `right_hand.png`: The hand sprite for the right arm.
*   `left_thigh.png`: The upper part of the left leg.
*   `left_leg.png`: The lower part of the left leg.
*   `left_arm.png`: The upper part of the left arm.
*   `left_hand.png`: The hand sprite for the left arm.
*   `head.png`: The sprite for the peasant's head.

## Usage in Modding

When creating or modifying ragdolls, understanding these file paths is crucial for:

*   **Replacing existing sprites:** You can substitute these `.png` files with your own custom artwork to change the appearance of the peasant ragdoll.
*   **Defining new ragdolls:** The structure of this file provides a template for how to organize sprite assets for other custom ragdolls.
*   **Physics and Animation Integration:** While this file only defines the visual assets, these sprites are linked to the ragdoll's physics properties and animations within other game data files.

**Note:** The exact positioning and scaling of these sprites are typically handled in associated configuration files (e.g., `.xml` or `.lua` files) that reference these image assets. This `filenames.txt` file solely lists the image files themselves.