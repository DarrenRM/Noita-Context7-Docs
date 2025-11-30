---
title: Slime Shooter (Non-Toxic Variant)
category: entities
---

# Slime Shooter (Non-Toxic Variant)

This entity defines a non-toxic variant of the Slime Shooter creature in Noita. It inherits most of its behavior and appearance from the base `slimeshooter.xml` file, with specific modifications to its projectile and damage components.

## Key Components and Attributes

### Base Entity Inheritance

The Slime Shooter (Non-Toxic) primarily inherits from `data/entities/animals/slimeshooter.xml`.

### AnimalAIComponent

This component governs the creature's AI behavior.

*   **`attack_ranged_entity_file`**: Specifies the projectile entity used for ranged attacks.
    *   `data/entities/projectiles/radioactive_blob.xml`: This indicates the creature shoots a radioactive blob.

### DamageModelComponent

This component defines how the creature takes damage and what happens upon taking damage.

*   **`blood_material`**: The material that constitutes the creature's blood when damaged.
    *   `radioactive_liquid_fading`: The blood will be a fading radioactive liquid.
*   **`blood_spray_material`**: The material that constitutes the blood spray when damaged.
    *   `radioactive_liquid_fading`: The blood spray will also be a fading radioactive liquid.

### MaterialInventoryComponent

This component is disabled for this variant.

*   **`_enabled="0"`**: This means the creature does not carry or utilize any specific materials in its inventory.

### Visual Components (Tentacles)

The Slime Shooter (Non-Toxic) entity includes several child entities that represent its visual tentacles. These are inherited from specificverlet chain files.

*   **Tentacle 1**:
    *   `Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_bright_02.xml"`
    *   `InheritTransformComponent`: Positioned at `x="0"`, `y="-6"`.
*   **Tentacle 2**:
    *   `Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_bright_01.xml"`
    *   `InheritTransformComponent`: Positioned at `x="-3"`, `y="-6"`.
*   **Tentacle 3**:
    *   `Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_thin_01.xml"`
    *   `InheritTransformComponent`: Positioned at `x="3"`, `y="-6"`.

---
```xml
<Entity name="$animal_slimeshooter">
  
	<Base file="data/entities/animals/slimeshooter.xml" >
		<AnimalAIComponent
			attack_ranged_entity_file="data/entities/projectiles/radioactive_blob.xml"
			>
		</AnimalAIComponent>
		
		<DamageModelComponent
			blood_material="radioactive_liquid_fading"
			blood_spray_material="radioactive_liquid_fading"
			>
		</DamageModelComponent>
		
		<MaterialInventoryComponent 
			_enabled="0" 
			>
		</MaterialInventoryComponent>
	</Base>
	
	<Entity>  <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_bright_02.xml"> <InheritTransformComponent><Transform position.x="0"  position.y="-6" ></Transform></InheritTransformComponent> </Base>  </Entity>
	<Entity>  <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_bright_01.xml"> <InheritTransformComponent><Transform position.x="-3" position.y="-6" ></Transform></InheritTransformComponent> </Base>  </Entity>
	<Entity>  <Base file="data/entities/verlet_chains/slime_tentacle/slime_tentacle_thin_01.xml"> <InheritTransformComponent><Transform position.x="3"  position.y="-6" ></Transform></InheritTransformComponent> </Base>  </Entity>

</Entity>
```