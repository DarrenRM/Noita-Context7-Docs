---
title: Basebot Neutralizer Ragdoll
category: ragdolls
---

# Basebot Neutralizer Ragdoll

This documentation describes the ragdoll configuration for the "neutralizer" variant of the basebot enemy in Noita.

## Ragdoll File Structure

The ragdoll is defined by a set of image files that dictate its visual appearance and animation frames.

### Key Image Files

*   **`neutralizer.png`**: The primary sprite sheet for the neutralizer ragdoll. This file contains all the visual frames for the ragdoll's animations.

## Ragdoll Properties

Ragdolls in Noita define how an entity's body behaves and animates when it's not actively controlled. For the neutralizer, this primarily concerns its visual representation and how it falls apart or reacts to damage.

### Important Attributes

While the `filenames_neutralizer.txt` file itself is minimal, the associated `.png` file implies the following:

*   **Animation Frames**: The `neutralizer.png` file contains distinct frames that represent different poses or stages of the ragdoll's animation (e.g., standing, falling, broken).
*   **Sprite Dimensions**: The dimensions of the `neutralizer.png` file determine the overall size of the ragdoll sprite.
*   **Collision/Hitboxes**: Although not explicitly defined in this text file, the arrangement of sprites within the `.png` can indirectly influence how hitboxes are applied during gameplay.
*   **Visual States**: Different sections of the sprite sheet likely correspond to various visual states of the ragdoll, such as intact, damaged, or completely disintegrated.

## Usage

This ragdoll configuration is applied to entities that utilize the "basebot" type and specifically the "neutralizer" variant. It dictates how these enemies will visually react to being defeated or taking significant damage.