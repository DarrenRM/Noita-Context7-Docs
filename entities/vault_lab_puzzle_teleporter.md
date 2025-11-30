---
title: Vault Lab Puzzle Teleporter
category: entities
---

# Vault Lab Puzzle Teleporter

This entity defines a teleporter puzzle within the vault laboratory. It inherits its base functionality from `vault_lab_puzzle_protect.xml`.

## Key Components

### Base Entity
*   Inherits from: `data/entities/buildings/vault_lab_puzzle_protect.xml`

### MaterialAreaCheckerComponent
This component checks for the presence of specific magic liquid materials within its area.

*   `material`: `magic_liquid_teleportation`
*   `material2`: `magic_liquid_unstable_teleportation`

### PixelSceneComponent
This component defines the visual background for the puzzle.

*   `pixel_scene_background`: `data/biome_impl/vault/lab_puzzle_tele_background.png`