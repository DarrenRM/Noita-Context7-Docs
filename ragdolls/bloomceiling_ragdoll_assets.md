---
title: Bloomceiling Ragdoll Assets
category: ragdolls
---

---

# Bloomceiling Ragdoll Assets

This documentation outlines the image assets used for the "Bloomceiling" ragdoll in Noita. These files define the visual components of the ragdoll's body parts.

## Asset Files

The following `.png` files are used to construct the Bloomceiling ragdoll:

*   `torso.png`: The main body segment of the ragdoll.
*   `flower.png`: A decorative or functional flower element.
*   `tentacle_1.png` through `tentacle_6.png`: Various tentacle segments, likely for animation or different attachment points.

## Usage

These image files are referenced by the game's ragdoll system to render the visual representation of the Bloomceiling entity when it is in a ragdoll state. Modders can potentially replace or modify these assets to alter the appearance of the Bloomceiling ragdoll.

## Key Attributes (Implied)

While the raw data only lists filenames, the game engine will interpret these based on their context within the ragdoll definition. Key attributes that would be associated with these assets include:

*   **Sprite Sheet:** Each `.png` likely acts as a sprite sheet containing multiple frames for animation.
*   **Pivot Points:** The game will define pivot points for each segment to facilitate proper rotation and attachment.
*   **Collision Shapes:** Associated collision data will be used for physics interactions.
*   **Layering:** The order in which these sprites are rendered will determine their visual depth.
*   **Animation Data:** Specific animation sequences will be defined to control how these sprites move.