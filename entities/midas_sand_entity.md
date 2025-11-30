---
title: Midas Sand Entity
category: entities
---

# Midas Sand Entity

This entity defines a special type of loose ground that behaves like "Midas Sand," implying it might have unique interactions or visual effects related to gold or transformation.

## Core Components

### LooseGroundComponent
This component dictates the behavior of the loose ground.

*   **`probability`**: `0.4` - The chance this ground will spawn or be generated.
*   **`max_distance`**: `160` - The maximum distance from the player or origin at which this ground can exist or be generated.
*   **`min_radius`**: `3` - The minimum radius of a chunk of this ground.
*   **`max_radius`**: `12` - The maximum radius of a chunk of this ground.
*   **`max_angle`**: `3.1415` - The maximum angle (in radians) for the overall shape of the ground chunk.
*   **`chunk_max_angle`**: `1.57` - The maximum angle (in radians) for sub-chunks within the main ground chunk.
*   **`chunk_probability`**: `0.0` - The probability of generating sub-chunks. Set to `0.0` means no sub-chunks are generated.
*   **`collapse_images`**: `data/procedural_gfx/collapse_big/$[0-14].png` - Specifies the image sequence used when this ground collapses.

### LifetimeComponent
This component controls how long the entity persists.

*   **`lifetime`**: `160` - The base duration in frames the entity will exist.
*   **`randomize_lifetime.min`**: `-50` - The minimum random variation to subtract from the base lifetime.
*   **`randomize_lifetime.max`**: `50` - The maximum random variation to add to the base lifetime.

## Entity Structure

The `Midas_sand.xml` entity is composed of two identical `Entity` blocks, each containing a `LooseGroundComponent` and an `InheritTransformComponent`. These two blocks are positioned symmetrically around the origin. A `LifetimeComponent` is applied to the parent `Entity`, affecting the overall duration of the combined structure.

```xml
<Entity>
	<Entity>
		<InheritTransformComponent>
			<Transform 
				position.x="-96"
				position.y="-64" 
				>
			</Transform>
		</InheritTransformComponent>
		
		<LooseGroundComponent
			probability="0.4"
			max_distance="160"
			min_radius="3"
			max_radius="12"
			max_angle="3.1415"
			chunk_max_angle="1.57"
			chunk_probability="0.0"
			collapse_images="data/procedural_gfx/collapse_big/$[0-14].png"
			_enabled="1"
			>
		</LooseGroundComponent>
	</Entity>
	
	<Entity>
		<InheritTransformComponent>
			<Transform 
				position.x="96"
				position.y="-64" 
				>
			</Transform>
		</InheritTransformComponent>
		
		<LooseGroundComponent
			probability="0.4"
			max_distance="160"
			min_radius="3"
			max_radius="12"
			max_angle="3.1415"
			chunk_max_angle="1.57"
			chunk_probability="0.0"
			collapse_images="data/procedural_gfx/collapse_big/$[0-14].png"
			_enabled="1"
			>
		</LooseGroundComponent>
	</Entity>
	
	<LifetimeComponent
		lifetime="160"
		randomize_lifetime.min="-50"
		randomize_lifetime.max="50"
		>
	</LifetimeComponent>
</Entity>
```