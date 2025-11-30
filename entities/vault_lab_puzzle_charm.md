---
title: Vault Lab Puzzle Charm
category: entities
---

# Vault Lab Puzzle Charm

This entity represents a puzzle element within the Vault Lab, specifically related to the "Charm" mechanic. It utilizes specific materials and a background image to define its visual and functional properties.

## Key Components

### Base Entity
Inherits functionality from `data/entities/buildings/vault_lab_puzzle_protect.xml`.

### MaterialAreaCheckerComponent (Primary)
This component defines the materials that trigger specific interactions.

*   **material**: `magic_liquid_charm`
*   **material2**: `magic_liquid_hp_regeneration`

### PixelSceneComponent
Defines the visual background for this puzzle element.

*   **pixel\_scene\_background**: `data/biome_impl/vault/lab_puzzle_charm_background.png`

### MaterialAreaCheckerComponent (Secondary)
This component appears to be for a secondary interaction or a failure condition check.

*   **area\_aabb.min\_x**: -3
*   **area\_aabb.max\_x**: 3
*   **area\_aabb.min\_y**: 6
*   **area\_aabb.max\_y**: 8
*   **update\_every\_x\_frame**: 10
*   **material**: `magic_liquid_hp_regeneration_unstable`
*   **material2**: `magic_liquid_hp_regeneration_unstable`
*   **look\_for\_failure**: 0 (Indicates this component doesn't actively look for failure states)
*   **kill\_after\_message**: 0 (Indicates the entity won't be killed after a message)