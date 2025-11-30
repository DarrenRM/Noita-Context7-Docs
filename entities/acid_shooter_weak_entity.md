---
title: Acid Shooter (Weak) Entity
category: entities
---

# Acid Shooter (Weak) Entity

This document details the `acidshooter_weak.xml` entity, a less potent variant of the standard Acid Shooter in Noita. It inherits most of its properties from the base `acidshooter.xml` but features reduced health and a distinct visual appearance.

## Key Attributes

The `acidshooter_weak.xml` entity primarily modifies the base Acid Shooter through the following components:

*   **`DamageModelComponent`**: This component defines the entity's health and how it reacts to damage.
    *   `hp`: Set to `0.4`, indicating significantly lower health compared to the standard Acid Shooter.
    *   `ragdoll_filenames_file`: Specifies the ragdoll files used when the entity is defeated, pointing to `data/ragdolls/acidshooter_weak/filenames.txt`.

*   **`SpriteComponent`**: This component dictates the visual representation of the entity.
    *   `image_file`: Points to `data/enemies_gfx/acidshooter_weak.xml`, providing the unique graphical assets for this weaker variant.

## Inherited Base Entity

This entity inherits its core functionality and behavior from the base `acidshooter.xml` file. This means it will likely share attack patterns, movement, and other AI behaviors with its stronger counterpart, but with adjusted parameters where overridden.

## Verlet Chains (Tentacles)

The Acid Shooter (Weak) utilizes several `verlet_chains` to form its tentacles. These are instantiated as separate entities with their own base files and transformations.

| Entity Base File                                       | Transform Position (x, y) |
| :----------------------------------------------------- | :------------------------ |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_alt_02.xml` | (-3, -1)                  |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_alt_01.xml` | (-4, -1)                  |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_alt_01.xml` | (0, -1)                   |
| `data/entities/verlet_chains/slime_tentacle/slime_tentacle_thin_alt_01.xml` | (4, -1)                   |

These tentacles are attached to the main entity and contribute to its overall appearance and potentially its attack mechanics.

```xml
<Entity name="$animal_acidshooter">
	<Base file="data/entities/animals/acidshooter.xml" >
		<DamageModelComponent
			ragdoll_filenames_file="data/ragdolls/acidshooter_weak/filenames.txt"
			hp="0.4"
			>
		</DamageModelComponent>
		
		<SpriteComponent 
			image_file="data/enemies_gfx/acidshooter_weak.xml" 
			>
		</SpriteComponent> 
	</Base>
	
	<Entity>  <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_alt_02.xml"> <InheritTransformComponent><Transform position.x="-3" position.y="-1" ></Transform></InheritTransformComponent> </Base>  </Entity>
	<Entity>  <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_alt_01.xml"> <InheritTransformComponent><Transform position.x="-4" position.y="-1" ></Transform></InheritTransformComponent> </Base>  </Entity>
	<Entity>  <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_alt_01.xml"> <InheritTransformComponent><Transform position.x="0"  position.y="-1" ></Transform></InheritTransformComponent> </Base>  </Entity>
	<Entity>  <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_thin_alt_01.xml"> <InheritTransformComponent><Transform position.x="4"  position.y="-1" ></Transform></InheritTransformComponent> </Base>  </Entity>
</Entity>
```