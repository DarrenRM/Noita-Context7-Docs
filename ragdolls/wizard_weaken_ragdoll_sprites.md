---
title: Wizard Weaken Ragdoll Sprites
category: ragdolls
---

# Wizard Weaken Ragdoll Sprites

This documentation describes the sprite assets used for the "wizard_weaken" ragdoll effect in Noita. These sprites define the visual appearance of the wizard's body parts when they are affected by this specific debuff.

## Sprite Files

The following PNG files define the individual body parts for the wizard_weaken ragdoll:

*   `torso.png`: Sprite for the wizard's torso.
*   `hand.png`: Sprite for the wizard's hand.
*   `feet.png`: Sprite for the wizard's feet.
*   `head.png`: Sprite for the wizard's head.

## Usage

These sprite files are intended to be referenced by Noita's internal systems when a wizard is under the "weaken" status effect. The game engine will use these images to render the detached body parts of the wizard as they fall or are otherwise affected by physics.

## Key Attributes (Implied)

While the raw data only provides filenames, the following attributes are implicitly important for these sprites:

*   **Image Dimensions:** The resolution of each PNG file will determine the size of the ragdoll parts.
*   **Transparency:** Alpha channels in the PNGs are crucial for proper rendering and blending with the game world.
*   **Sprite Sheet/Individual Files:** The organization of these files (whether they are part of a larger sprite sheet or individual assets) impacts how they are loaded and used by the game.
*   **Animation Frames:** If these sprites are intended for animation (e.g., a falling animation), they would likely be part of a sequence or have associated frame data.
*   **Pivot Points:** The internal pivot points of these sprites are critical for correct rotation and positioning when physics are applied.