---
title: Roboguard Ragdoll Sprites
category: ragdolls
---

# Roboguard Ragdoll Sprites

This documentation outlines the sprite assets used for the Roboguard's ragdoll. These files define the visual components of the Roboguard when it is defeated and its body breaks apart.

## Sprite Components

The following PNG files represent individual parts of the Roboguard's ragdoll. These are typically used in conjunction with a `ragdoll.xml` file to define how these parts connect and animate.

### Torso

*   `data/ragdolls/roboguard/torso.png`: The central body segment of the Roboguard.

### Limbs

*   `data/ragdolls/roboguard/right_thigh.png`: The upper part of the Roboguard's right leg.
*   `data/ragdolls/roboguard/right_foot.png`: The foot of the Roboguard's right leg.
*   `data/ragdolls/roboguard/right_shoulder.png`: The shoulder joint for the Roboguard's right arm.
*   `data/ragdolls/roboguard/right_arm.png`: The upper and lower arm segments for the Roboguard's right arm.
*   `data/ragdolls/roboguard/right_hand.png`: The hand of the Roboguard's right arm.
*   `data/ragdolls/roboguard/left_thigh.png`: The upper part of the Roboguard's left leg.
*   `data/ragdolls/roboguard/left_foot.png`: The foot of the Roboguard's left leg.
*   `data/ragdolls/roboguard/left_arm.png`: The upper and lower arm segments for the Roboguard's left arm.
*   `data/ragdolls/roboguard/left_hand.png`: The hand of the Roboguard's left arm.

### Connectors

*   `data/ragdolls/roboguard/cord_1.png`: A sprite representing a connecting cord or wire.
*   `data/ragdolls/roboguard/cord_2.png`: Another sprite representing a connecting cord or wire.

## Usage Notes

These sprite files are essential for creating a visually distinct ragdoll effect for the Roboguard enemy. Modders can leverage these assets by referencing them within their custom `ragdoll.xml` configurations to define the physics and appearance of the broken Roboguard.