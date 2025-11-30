---
title: Shotgunner (Weak Variant) Entity
category: entities
---

# Shotgunner (Weak Variant) Entity

This document describes the `shotgunner_weak.xml` entity, a less powerful variant of the standard Shotgunner enemy in Noita.

## Entity Definition

The `shotgunner_weak` entity inherits its core properties from `data/entities/animals/shotgunner.xml` and modifies specific components.

```xml
<Entity name="$animal_shotgunner">
	<Base file="data/entities/animals/shotgunner.xml" include_children="1" >
		<DamageModelComponent
			ragdoll_filenames_file="data/ragdolls/shotgunner_weak/filenames.txt"
			hp="0.36"
			>
		</DamageModelComponent>
		
		<SpriteComponent 
			image_file="data/enemies_gfx/shotgunner_weak.xml" 
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

*   **`file`**: `data/entities/animals/shotgunner.xml` - Inherits all properties from the standard Shotgunner.
*   **`include_children`**: `1` - Ensures all child components from the base entity are included.

### DamageModelComponent

This component defines the health and damage-related properties of the entity.

*   **`hp`**: `0.36` - Represents the health points of this weak variant. This is significantly lower than the standard Shotgunner, making it easier to defeat.
*   **`ragdoll_filenames_file`**: `data/ragdolls/shotgunner_weak/filenames.txt` - Specifies the files used for the ragdoll physics when the entity is defeated. This points to a specific set of ragdoll assets for the weak variant.

### SpriteComponent

This component handles the visual representation of the entity.

*   **`image_file`**: `data/enemies_gfx/shotgunner_weak.xml` - Defines the graphical assets used for this weak Shotgunner. This points to a distinct set of sprites compared to the standard variant.

### MusicEnergyAffectorComponent

This component influences the game's music based on the entity's presence or state.

*   **`energy_target`**: `0.5` - Indicates the target energy level for the music system when this entity is active. A value of `0.5` suggests a moderate influence on the music's intensity or mood.