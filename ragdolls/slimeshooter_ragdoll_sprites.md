---
title: Slimeshooter Ragdoll Sprites
category: ragdolls
---

# Slimeshooter Ragdoll Sprites

This documentation outlines the sprite assets used for the "slimeshooter" ragdoll in Noita. These files define the visual components of the ragdoll when it is in a non-animated, physics-driven state.

## Key Sprite Components

The slimeshooter ragdoll is composed of several distinct sprite elements, primarily representing its torso and various tentacle segments.

### Torso Sprite

*   **`torso.png`**: This sprite defines the main body of the slimeshooter. It serves as the central anchor for the ragdoll's physics and other attached components.

### Tentacle Sprites

The slimeshooter features multiple tentacle segments, likely used to create a more dynamic and fluid ragdoll effect. These are organized into pairs, suggesting different states or animation frames for each tentacle.

*   **`tentacle_1_a.png` / `tentacle_1_b.png`**: Represents the first set of tentacle sprites.
*   **`tentacle_2_a.png` / `tentacle_2_b.png`**: Represents the second set of tentacle sprites.
*   **`tentacle_3_a.png` / `tentacle_3_b.png`**: Represents the third set of tentacle sprites.
*   **`tentacle_4_a.png` / `tentacle_4_b.png`**: Represents the fourth set of tentacle sprites.

These paired sprites (`_a` and `_b`) might be used for subtle variations in pose or to allow for a basic form of "animation" within the ragdoll system, such as slight swaying or twitching.

## Usage in Modding

When creating or modifying ragdolls for AI entities, these sprite files would be referenced in the entity's configuration to define its visual appearance when it's not actively performing an action or is defeated. Understanding these components is crucial for:

*   **Visual Customization**: Replacing or altering these sprites to change the appearance of the slimeshooter ragdoll.
*   **Ragdoll Behavior**: While sprites define appearance, their arrangement and connection points (defined elsewhere in the ragdoll configuration) influence how the ragdoll behaves physically.
*   **Performance**: The resolution and complexity of these sprites can impact game performance.