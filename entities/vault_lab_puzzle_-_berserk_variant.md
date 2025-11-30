---
title: Vault Lab Puzzle - Berserk Variant
category: entities
---

# Vault Lab Puzzle - Berserk Variant

This entity defines a specific variant of the "Vault Lab Puzzle" building, characterized by its use of the "berserk" magic liquid.

## Key Components

### Base Entity
*   **Inheritance:** Inherits from `data/entities/buildings/vault_lab_puzzle_protect.xml`. This means it shares many core properties with the standard "protect" variant of the vault lab puzzle.

### MaterialAreaCheckerComponent
*   **Purpose:** This component is crucial for detecting the presence of specific materials within the entity's area.
*   **Key Attributes:**
    *   `material`: `magic_liquid_berserk` - The primary material that this component checks for.
    *   `material2`: `magic_liquid_berserk` - The secondary material check, also set to `magic_liquid_berserk` in this case. This likely reinforces the requirement for the berserk liquid.

### PixelSceneComponent
*   **Purpose:** Manages the visual representation of the entity using pixel art.
*   **Key Attributes:**
    *   `pixel_scene_background`: `data/biome_impl/vault/lab_puzzle_berserk_background.png` - Specifies the background image used for this specific berserk variant of the lab puzzle. This differentiates its visual appearance from other variants.