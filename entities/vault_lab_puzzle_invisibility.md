---
title: Vault Lab Puzzle (Invisibility)
category: entities
---

# Vault Lab Puzzle (Invisibility)

This entity defines a puzzle element within a vault laboratory that utilizes invisibility. It inherits its base functionality from `vault_lab_puzzle_protect.xml` and adds specific properties related to invisibility.

## Key Attributes

*   **`tags`**: `vault_lab_puzzle` - Identifies this entity as a vault lab puzzle.
*   **`Base`**: Inherits from `data/entities/buildings/vault_lab_puzzle_protect.xml`.

## Components

### MaterialAreaCheckerComponent

This component checks for the presence of specific materials within an area.

*   **`material`**: `magic_liquid_invisibility` - The primary material to detect.
*   **`material2`**: `magic_liquid_invisibility` - The secondary material to detect (in this case, the same as the primary).

### PixelSceneComponent

This component handles the visual representation of the puzzle.

*   **`pixel_scene_background`**: `data/biome_impl/vault/lab_puzzle_invis_background.png` - Specifies the background image for this puzzle element.