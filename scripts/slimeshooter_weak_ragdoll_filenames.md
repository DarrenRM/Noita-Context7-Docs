---
title: Slimeshooter Weak Ragdoll Filenames
category: data/ragdolls
---

```

# Slimeshooter Weak Ragdoll Filenames

This document lists the filenames for the ragdoll assets associated with the "slimeshooter_weak" entity in Noita. These files define the visual components of the entity's ragdoll when it is defeated or affected by physics.

## Filename Breakdown

The following files represent the individual sprite components for the slimeshooter_weak ragdoll:

*   `torso.png`: The primary body segment of the ragdoll.
*   `tentacle_1_a.png`: A variant of the first tentacle.
*   `tentacle_1_b.png`: Another variant of the first tentacle.
*   `tentacle_2_a.png`: A variant of the second tentacle.
*   `tentacle_2_b.png`: Another variant of the second tentacle.
*   `tentacle_4_a.png`: A variant of the fourth tentacle.
*   `tentacle_4_b.png`: Another variant of the fourth tentacle.

## Key Elements

*   **`torso.png`**: This is the central piece of the ragdoll, likely dictating the main collision and physics behavior.
*   **Tentacle Variants (`_a.png`, `_b.png`)**: The presence of multiple variants for tentacles suggests a degree of randomness or variation in how the ragdoll pieces will orient and move, contributing to a more dynamic and less predictable ragdoll effect.
*   **Naming Convention**: The `tentacle_X_Y.png` format indicates a structured approach to defining different limbs or appendages and their variations.

## Usage in Modding

When creating or modifying entities that utilize ragdolls, understanding these filenames is crucial for:

*   **Replacing or adding new ragdoll sprites**: Modders can swap out existing `.png` files with their own custom artwork.
*   **Adjusting ragdoll physics**: While not directly defined here, the number and arrangement of these sprite files influence how the ragdoll behaves in the game engine.
*   **Troubleshooting visual glitches**: Incorrectly named or missing files can lead to visual errors in the ragdoll.