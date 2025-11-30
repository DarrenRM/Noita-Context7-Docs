---
title: Vault Lab Puzzle Worm
category: entities
---

# Vault Lab Puzzle Worm

This entity defines a puzzle element within the Vault Lab, specifically related to the "worm" mechanic. It inherits its base functionality from `vault_lab_puzzle_protect.xml`.

## Key Components

### Base Entity

*   **Inheritance:** `data/entities/buildings/vault_lab_puzzle_protect.xml` - This indicates it reuses the core structure and properties of a protected vault lab puzzle.

### MaterialAreaCheckerComponent

This component is crucial for detecting specific materials within its area of influence.

*   **`material`**: `magic_liquid_worm_attractor`
    *   This material likely acts as a trigger or a key element for the puzzle's worm-related mechanics.
*   **`material2`**: `blood_worm`
    *   This material is also detected, suggesting a relationship or interaction with "blood worms" within the puzzle.

### PixelSceneComponent

This component handles the visual representation of the entity.

*   **`pixel_scene_background`**: `data/biome_impl/vault/lab_puzzle_worm_background.png`
    *   Specifies the background image used for this puzzle element, contributing to its visual theme within the vault lab.