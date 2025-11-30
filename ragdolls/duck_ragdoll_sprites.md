---
title: Duck Ragdoll Sprites
category: ragdolls
---

# Duck Ragdoll Sprites

This documentation describes the sprite assets used for the duck ragdoll in Noita. These files define the visual appearance of the duck when it is in a ragdoll state.

## Sprite Files

The following PNG files are used to construct the duck ragdoll:

*   `torso.png`: The main body sprite of the duck.
*   `head.png`: The sprite for the duck's head.
*   `feet.png`: The sprite for the duck's feet.

These sprites are typically combined and animated by the game engine to create the ragdoll effect.

## Usage

These sprites are referenced within the Noita data files, specifically in the configuration for entities that utilize the duck ragdoll. They are located in the `data/ragdolls/duck/` directory.

## AI Modding Considerations

When modding Noita with AI assistance, understanding these sprite assets is crucial for:

*   **Visual Consistency:** Ensuring new entities or modifications maintain the intended visual style.
*   **Asset Replacement:** Replacing existing ragdoll sprites with custom ones.
*   **Animation Logic:** Understanding how sprites are intended to be used in conjunction with animation systems.

It's important to note that the actual ragdoll physics and behavior are controlled by separate script and configuration files, not directly by these sprite assets.