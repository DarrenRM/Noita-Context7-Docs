---
title: Giant Shooter Ragdoll Sprites
category: ragdolls
---

# Giant Shooter Ragdoll Sprites

This documentation outlines the sprite files used for the "Giant Shooter" entity's ragdoll. These files define the visual components of the entity when it is in a ragdoll state.

## Key Sprite Components

The ragdoll for the Giant Shooter is composed of a torso and multiple tentacle segments. Each segment has two variations (a and b), likely for animation or slight visual differences.

### Torso

*   **`torso.png`**: This file represents the main body of the Giant Shooter.

### Tentacles

The tentacles are broken down into several segments, each with two distinct sprite files.

*   **Tentacle 1**:
    *   `tentacle_1_a.png`
    *   `tentacle_1_b.png`
*   **Tentacle 2**:
    *   `tentacle_2_a.png`
    *   `tentacle_2_b.png`
*   **Tentacle 3**:
    *   `tentacle_3_a.png`
    *   `tentacle_3_b.png`
*   **Tentacle 4**:
    *   `tentacle_4_a.png`
    *   `tentacle_4_b.png`
*   **Tentacle 5**:
    *   `tentacle_5_a.png`
    *   `tentacle_5_b.png`
*   **Tentacle 6**:
    *   `tentacle_6_a.png`
    *   `tentacle_6_b.png`

## Usage in Modding

When creating or modifying entities that utilize this ragdoll, these sprite files would be referenced in the entity's configuration or associated Lua scripts to define its appearance upon death or when ragdolling. The `a` and `b` variations might be used for random selection, animation frames, or different states of the tentacle.