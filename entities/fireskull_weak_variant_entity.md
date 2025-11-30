---
title: Fireskull (Weak Variant) Entity
category: entities
---

# Fireskull (Weak Variant) Entity

This document details the configuration for a weaker variant of the Fireskull enemy in Noita, primarily intended for AI-assisted modding.

## Entity Definition

The Fireskull (weak) entity inherits its core properties from the base `fireskull.xml` file.

```xml
<Entity name="$animal_fireskull">
  
	<Base file="data/entities/animals/fireskull.xml" >
		<DamageModelComponent
			hp="0.4"
			>
		</DamageModelComponent>
		
		<SpriteComponent 
			image_file="data/enemies_gfx/fireskull.xml" 
			>
		</SpriteComponent> 
	</Base>

</Entity>
```

## Key Components and Attributes

### Base Entity Inheritance

*   **`Base file="data/entities/animals/fireskull.xml"`**: This indicates that the Fireskull (weak) entity is a derivative of the standard Fireskull. Modifications here are layered on top of the base entity's properties.

### DamageModelComponent

*   **`hp="0.4"`**: This is the primary attribute defining the "weak" nature of this variant. It has significantly reduced hit points compared to the base Fireskull, making it easier to defeat.

### SpriteComponent

*   **`image_file="data/enemies_gfx/fireskull.xml"`**: This specifies the graphical assets used for the Fireskull. This variant uses the same visual representation as the standard Fireskull, differentiating itself only in combat stats.

## Summary

The Fireskull (weak) entity is a simplified version of the standard Fireskull, characterized by its drastically reduced HP. It reuses the graphical assets of its parent entity, making it visually indistinguishable from the regular Fireskull but much less durable. This makes it suitable for scenarios requiring less challenging enemies or for early-game encounters.