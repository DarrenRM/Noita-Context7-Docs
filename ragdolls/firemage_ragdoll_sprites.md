---
title: Firemage Ragdoll Sprites
category: ragdolls
---

# Firemage Ragdoll Sprites

This documentation outlines the sprite assets used for the Firemage's ragdoll in Noita. These files define the visual components of the character's body when it breaks apart.

## Sprite Components

The following PNG files represent individual parts of the Firemage's ragdoll. These are typically used in conjunction with animation and physics to create the ragdoll effect.

### Key Sprites

*   `torso.png`: The main body segment.
*   `head.png`: The character's head.
*   `hood.png`: The hood worn by the character.
*   `right_arm.png`: The right arm.
*   `right_hand.png`: The right hand.
*   `right_thigh.png`: The right thigh.
*   `right_foot.png`: The right foot.
*   `left_arm.png`: The left arm.
*   `left_hand.png`: The left hand.
*   `left_thigh.png`: The left thigh.
*   `left_foot.png`: The left foot.

## Usage

These sprite files are referenced by the game's entity definitions and animation systems. When a Firemage entity is destroyed or its physics are disrupted, these sprites are used to render the detached body parts. Modders can potentially replace or modify these sprites to alter the visual appearance of the Firemage's ragdoll.