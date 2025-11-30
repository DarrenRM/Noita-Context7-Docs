---
title: Vault Lab Puzzle - Polymorph
category: guides
---

<Entity tags="vault_lab_puzzle">
	<Base file="data/entities/buildings/vault_lab_puzzle_protect.xml">
		<MaterialAreaCheckerComponent
			material="magic_liquid_polymorph"
			material2="magic_liquid_random_polymorph" >
		</MaterialAreaCheckerComponent>
		<PixelSceneComponent
			pixel_scene_background="data/biome_impl/vault/lab_puzzle_poly_background.png" >
		</PixelSceneComponent>
	</Base>
</Entity>
```

---
title: Vault Lab Puzzle - Polymorph
category: entities
---

# Vault Lab Puzzle - Polymorph

This entity represents a puzzle element within a vault laboratory environment in Noita. It's designed to interact with polymorph magic liquids.

## Key Components

*   **`Base`**: Inherits functionality from `data/entities/buildings/vault_lab_puzzle_protect.xml`, suggesting it's a protected puzzle element.
*   **`MaterialAreaCheckerComponent`**:
    *   `material`: "magic_liquid_polymorph" - Detects the presence of standard polymorph magic liquid.
    *   `material2`: "magic_liquid_random_polymorph" - Detects the presence of random polymorph magic liquid. This component is crucial for triggering puzzle mechanics based on liquid interaction.
*   **`PixelSceneComponent`**:
    *   `pixel_scene_background`: "data/biome_impl/vault/lab_puzzle_poly_background.png" - Specifies the background image for this puzzle element, likely contributing to the visual theme of the vault laboratory.

## Purpose

This entity is likely part of a larger puzzle system within vault labs. Its primary function is to react to the presence of polymorph magic liquids, potentially triggering events, transformations, or unlocking pathways when these specific materials are detected in its vicinity.