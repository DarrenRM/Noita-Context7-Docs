---
title: Miner (Weak) Entity
category: entities
---

# Miner (Weak) Entity

This document describes the configuration for a weaker variant of the Miner enemy entity in Noita, intended for AI-assisted modding.

## Entity Definition

The `miner_weak.xml` file defines a specific variant of the Miner entity. It inherits its core functionality from a base `miner.xml` file and overrides certain components to adjust its behavior and appearance.

```xml
<Entity name="$animal_miner">
	<Base file="data/entities/animals/miner.xml" include_children="1" >
		<DamageModelComponent
			ragdoll_filenames_file="data/ragdolls/miner_weak/filenames.txt"
			hp="0.44"
			>
		</DamageModelComponent>
		
		<SpriteComponent 
			image_file="data/enemies_gfx/miner_weak.xml" 
			>
		</SpriteComponent> 
	</Base>

    <MusicEnergyAffectorComponent
    	energy_target="0.5">
    </MusicEnergyAffectorComponent>

</Entity>
```

## Key Components and Attributes

### Base Entity

*   **`Base file="data/entities/animals/miner.xml" include_children="1"`**: This indicates that `miner_weak.xml` is a derivative of the standard `miner.xml` entity. All properties and components from the base file are inherited, and `include_children="1"` ensures that nested elements are also included.

### DamageModelComponent

*   **`hp="0.44"`**: This is a crucial attribute that defines the health of this weak miner variant. It has significantly less health (0.44) compared to a standard miner, making it easier to defeat.
*   **`ragdoll_filenames_file="data/ragdolls/miner_weak/filenames.txt"`**: Specifies the file containing the filenames for the ragdoll physics when this entity is defeated. This allows for a distinct ragdoll appearance for the weak variant.

### SpriteComponent

*   **`image_file="data/enemies_gfx/miner_weak.xml"`**: This attribute points to the graphical asset file used to render the weak miner. It ensures that this variant has a unique visual representation, likely differing from the standard miner's sprites.

### MusicEnergyAffectorComponent

*   **`energy_target="0.5"`**: This component influences the game's music based on the entity's presence. `energy_target="0.5"` suggests it contributes to a moderate level of "energy" that affects the music system, potentially making the music slightly more intense or dynamic when this entity is nearby.