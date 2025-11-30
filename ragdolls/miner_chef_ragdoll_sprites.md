---
title: Miner Chef Ragdoll Sprites
category: ragdolls
---

# Miner Chef Ragdoll Sprites

This documentation describes the sprite assets used to construct the "miner_chef" ragdoll in Noita. These files define the visual components of the character's ragdoll physics.

## Sprite Components

The following image files are used to assemble the miner chef's ragdoll. Each file represents a distinct body part.

### Key Sprites

*   `head.png`: The sprite for the character's head.
*   `torso.png`: The sprite for the character's torso.
*   `left_arm.png`: The sprite for the character's left arm.
*   `right_arm.png`: The sprite for the character's right arm.
*   `left_hand.png`: The sprite for the character's left hand.
*   `right_hand.png`: The sprite for the character's right hand.
*   `thighs.png`: The sprite for the character's thighs.
*   `left_foot.png`: The sprite for the character's left foot.
*   `right_foot.png`: The sprite for the character's right foot.
*   `fuse.png`: A sprite likely used for a specific animation or effect related to the miner chef, possibly a fuse for an explosive.

## Usage

These sprites are referenced by the ragdoll definition files (not included in this source) which dictate how these visual components are attached and behave under physics simulation. AI modding tools can use this information to understand the visual structure of existing ragdolls and potentially generate new ones or modify existing ones by referencing these sprite names and their intended body part.