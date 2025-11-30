---
title: Scavenger Glue Ragdoll Sprites
category: ragdolls
---

# Scavenger Glue Ragdoll Sprites

This documentation describes the sprite assets used for the "Scavenger Glue" ragdoll in Noita. These files define the visual appearance of the ragdoll's individual body parts when it is destroyed or dismembered.

## Sprite Files

The following PNG files are used to construct the Scavenger Glue ragdoll. Each file represents a distinct body part.

| Body Part   | Filename              |
| :---------- | :-------------------- |
| Torso       | `torso.png`           |
| Thighs      | `thighs.png`          |
| Head        | `head.png`            |
| Left Foot   | `left_foot.png`       |
| Right Foot  | `right_foot.png`      |
| Left Hand   | `left_hand.png`       |
| Right Hand  | `right_hand.png`      |

## Usage

These sprite files are typically referenced within the game's entity or object definitions to define how a specific entity's ragdoll should be rendered. When an entity with this ragdoll is destroyed, the game will use these images to create the visual effect of its body parts scattering.

## AI Modding Considerations

When creating AI-assisted mods that interact with or modify ragdoll behavior, understanding these sprite assets can be useful for:

*   **Visual Consistency:** Ensuring custom ragdolls or modifications align with the game's existing visual style.
*   **Entity Identification:** Potentially identifying entities based on their ragdoll sprite if direct entity definitions are not readily available.
*   **Asset Replacement:** Replacing existing ragdoll sprites with custom artwork.