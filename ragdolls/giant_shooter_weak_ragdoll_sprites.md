---
title: Giant Shooter Weak Ragdoll Sprites
category: ragdolls
---

# Giant Shooter Weak Ragdoll Sprites

This documentation outlines the sprite assets used for the "Giant Shooter Weak" enemy's ragdoll in Noita. These files define the visual components of the enemy when it is defeated and its body breaks apart.

## Core Components

The ragdoll is composed of a central torso and several tentacle segments. Each segment has two variations (a and b), likely for animation or slight visual differences.

### Torso

*   `data/ragdolls/giantshooter_weak/torso.png`: The primary sprite for the enemy's main body.

### Tentacles

The tentacles are broken down into multiple segments, each with two distinct sprite files.

*   `tentacle_1_a.png`
*   `tentacle_1_b.png`
*   `tentacle_2_a.png`
*   `tentacle_2_b.png`
*   `tentacle_3_a.png`
*   `tentacle_3_b.png`
*   `tentacle_4_a.png`
*   `tentacle_4_b.png`
*   `tentacle_5_a.png`
*   `tentacle_5_b.png`
*   `tentacle_6_a.png`
*   `tentacle_6_b.png`

## Usage in Modding

These `.png` files are directly referenced by the game's entity definitions and ragdoll configurations. Modders can:

*   **Replace Sprites:** Substitute these `.png` files with custom artwork to change the appearance of the Giant Shooter Weak's ragdoll.
*   **Modify Ragdoll Behavior:** While these files only define the visuals, they are intrinsically linked to the entity's ragdoll properties defined elsewhere (e.g., in `.xml` files). Changes to sprites might necessitate adjustments to associated physics or collision data for a cohesive effect.
*   **Create New Ragdolls:** These files can serve as a template or source of assets for creating entirely new ragdoll types for custom entities.