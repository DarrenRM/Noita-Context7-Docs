---
title: Vault Lab Puzzle - Speed
category: entities
---

# Vault Lab Puzzle - Speed

This entity defines a puzzle element within the Vault Lab, specifically designed to affect player movement speed. It utilizes special magic liquids to grant enhanced levitation and movement capabilities when the player is within its designated area.

## Key Components

### Base Entity
*   Inherits functionality from `data/entities/buildings/vault_lab_puzzle_protect.xml`. This suggests a common structure for vault lab puzzles, likely including visual elements and basic interaction logic.

### `MaterialAreaCheckerComponent` (Primary)
This component is responsible for detecting specific materials within a defined area and applying effects.

*   **`material`**: `magic_liquid_faster_levitation` - The primary material that triggers the speed enhancement.
*   **`material2`**: `magic_liquid_movement_faster` - A secondary material that complements the primary effect, further boosting movement.

### `PixelSceneComponent`
This component handles the visual representation of the puzzle element.

*   **`pixel_scene_background`**: `data/biome_impl/vault/lab_puzzle_speed_background.png` - Specifies the background image used for this puzzle's visual presentation.

### `MaterialAreaCheckerComponent` (Secondary)
This component defines the specific area and conditions for the speed-altering effect.

*   **`area_aabb.min_x`**: `-3`
*   **`area_aabb.max_x`**: `3`
*   **`area_aabb.min_y`**: `6`
*   **`area_aabb.max_y`**: `8`
    *   These define a rectangular bounding box relative to the entity's origin, specifying the zone where the material effects are active.
*   **`update_every_x_frame`**: `10` - The component's checks will run every 10 frames, optimizing performance.
*   **`material`**: `magic_liquid_faster_levitation_and_movement` - The material to look for within the defined area.
*   **`material2`**: `magic_liquid_faster_levitation_and_movement` - The secondary material to look for.
*   **`look_for_failure`**: `0` - This puzzle does not have a failure condition based on material presence.
*   **`kill_after_message`**: `0` - The entity will not be destroyed after displaying a message.

---
```xml
<Entity tags="vault_lab_puzzle">
	<Base file="data/entities/buildings/vault_lab_puzzle_protect.xml">
		<MaterialAreaCheckerComponent
			material="magic_liquid_faster_levitation"
			material2="magic_liquid_movement_faster" >
		</MaterialAreaCheckerComponent>
		<PixelSceneComponent
			pixel_scene_background="data/biome_impl/vault/lab_puzzle_speed_background.png" >
		</PixelSceneComponent>
	</Base>

	<MaterialAreaCheckerComponent
		area_aabb.min_x="-3" 
		area_aabb.max_x="3" 
		area_aabb.min_y="6"   
		area_aabb.max_y="8" 
		update_every_x_frame="10"
		material="magic_liquid_faster_levitation_and_movement"
		material2="magic_liquid_faster_levitation_and_movement"
		look_for_failure="0"
		kill_after_message="0" >
	</MaterialAreaCheckerComponent>
</Entity>
```