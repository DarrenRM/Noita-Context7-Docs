---
title: Scavenger Clusterbomb Ragdoll Sprites
category: ragdolls
---

# Scavenger Clusterbomb Ragdoll Sprites

This documentation outlines the sprite assets used for the "Scavenger Clusterbomb" ragdoll in Noita. These files define the visual components of the ragdoll when it is destroyed or dismembered.

## Sprite Components

The following image files are used to construct the ragdoll:

*   `torso_upper.png`: The upper section of the scavenger's torso.
*   `torso_lower.png`: The lower section of the scavenger's torso.
*   `left_thigh.png`: The left thigh segment.
*   `right_thigh.png`: The right thigh segment.
*   `head.png`: The scavenger's head.
*   `gun.png`: The scavenger's weapon, which detaches as a separate sprite.
*   `left_foot.png`: The left foot segment.
*   `right_foot.png`: The right foot segment.
*   `arm.png`: A generic arm segment (likely used for both left and right arms if they are identical).
*   `hand.png`: A generic hand segment (likely used for both left and right hands if they are identical).

## Usage

These `.png` files are referenced within the game's entity or ragdoll definition files (typically in `.xml` format) to specify how the ragdoll should be visually represented when its constituent parts are separated. Each sprite would be assigned a specific position and orientation relative to the ragdoll's center of mass upon destruction.