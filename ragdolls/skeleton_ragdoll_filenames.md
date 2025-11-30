---
title: Skeleton Ragdoll Filenames
category: ragdolls
---

# Skeleton Ragdoll Filenames

This document lists the filenames for the individual sprite components that make up the default skeleton ragdoll in Noita. These files are essential for defining the visual appearance and structure of the ragdoll physics.

## Core Components

The skeleton ragdoll is composed of several distinct sprite files, each representing a body part. These are typically used in conjunction with physics definitions to create the ragdoll effect.

### Sprite Files

*   `torso.png`: The main body sprite.
*   `head.png`: The head sprite.
*   `left_arm.png`: The left arm sprite.
*   `left_hand.png`: The left hand sprite.
*   `right_arm.png`: The right arm sprite.
*   `right_hand.png`: The right hand sprite.
*   `left_leg.png`: The left leg sprite.
*   `left_foot.png`: The left foot sprite.
*   `right_leg.png`: The right leg sprite.
*   `right_foot.png`: The right foot sprite.

## Usage in Modding

These filenames are referenced within Noita's data files, primarily in XML or Lua scripts that define entities and their physics properties. Modders can:

*   **Replace Sprites:** Substitute these default `.png` files with custom artwork to change the appearance of the skeleton ragdoll.
*   **Define New Ragdolls:** Use these filenames as a template or reference when creating entirely new ragdoll entities with custom sprite sets.
*   **Adjust Physics:** While not directly defined here, the structure implied by these filenames is crucial for setting up joint constraints and physics behaviors in related configuration files.

## Related Files

Modding the skeleton ragdoll typically involves referencing these sprite files in conjunction with:

*   **Physics Definitions:** XML files that define the physical properties, joints, and constraints of ragdoll entities.
*   **Entity Definitions:** XML files that link sprites, physics, and other behaviors to create in-game entities.