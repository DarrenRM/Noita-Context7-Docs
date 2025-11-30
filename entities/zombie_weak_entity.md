---
title: Zombie (Weak) Entity
category: entities
---

# Zombie (Weak) Entity

This document describes the `zombie_weak.xml` entity, a less durable variant of the standard zombie in Noita.

## Entity Definition

The `zombie_weak` entity inherits its core properties from `data/entities/animals/zombie.xml`.

```xml
<Entity tags="zombie" name="$animal_zombie">
  
	<Base file="data/entities/animals/zombie.xml" >
		<DamageModelComponent
			ragdoll_filenames_file="data/ragdolls/zombie_weak/filenames.txt"
			hp="0.2"
			>
		</DamageModelComponent>
		
		<SpriteComponent 
			image_file="data/enemies_gfx/zombie_weak.xml" 
			>
		</SpriteComponent> 
	</Base>

</Entity>
```

## Key Components and Attributes

### Base Entity

*   **`file`**: `data/entities/animals/zombie.xml` - Inherits all properties from the standard zombie.

### DamageModelComponent

This component modifies the zombie's survivability.

*   **`hp`**: `0.2` - Significantly reduced health compared to the standard zombie, making it much easier to defeat.
*   **`ragdoll_filenames_file`**: `data/ragdolls/zombie_weak/filenames.txt` - Specifies the ragdoll files used when this zombie is defeated.

### SpriteComponent

This component defines the visual appearance of the weak zombie.

*   **`image_file`**: `data/enemies_gfx/zombie_weak.xml` - Points to the specific sprite definition for the weak zombie variant.