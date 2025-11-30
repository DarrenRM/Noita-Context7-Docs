---
title: Stone Pile Prop
category: entities
---

# Stone Pile Prop

This entity defines a decorative "stone pile" prop in the game. It's composed of multiple individual physics-based stone entities loaded at specific relative positions.

## Key Components

### `Entity` (Root)

*   **`name`**: `unknown` (This is a placeholder and can be renamed for clarity in mods).
*   **`tags`**: `prop_physics` - Indicates this entity is a physical prop.

### `InheritTransformComponent` and `Transform`

These components are used within each sub-entity to define the relative position of the loaded stone.

*   **`position.x`**: X-coordinate offset.
*   **`position.y`**: Y-coordinate offset.

### `LoadEntitiesComponent`

This component is responsible for loading other entity files. In this case, it loads individual stone entities to form the pile.

*   **`count.min`**: Minimum number of entities to load (0).
*   **`count.max`**: Maximum number of entities to load (1). This means each stone is loaded at most once.
*   **`kill_entity`**: If set to 1, the parent entity would be destroyed after loading. Here it's 0, so the pile remains.
*   **`entity_file`**: The path to the entity file to load. This points to various `physics_stone_XX.xml` files, creating variety in the pile.

### `LifetimeComponent`

*   **`lifetime`**: `10` - The number of seconds this stone pile will exist before disappearing.

## Structure Breakdown

The `stonepile.xml` entity is structured as a parent entity containing multiple child `Entity` blocks. Each child `Entity` block defines a single stone within the pile.

```xml
<Entity name="unknown" tags="prop_physics" >

	<!-- First stone, offset slightly up and to the right -->
	<Entity>
		<InheritTransformComponent>
			<Transform 
				position.x="12"
				position.y="12" 
				>
			</Transform>
		</InheritTransformComponent>
		
		<LoadEntitiesComponent
			count.min="0"
			count.max="1"
			kill_entity="0"
			entity_file="data/entities/props/physics_stone_01.xml"
			>
		</LoadEntitiesComponent>
	</Entity>
	
	<!-- Second stone, offset directly up -->
	<Entity>
		<InheritTransformComponent>
			<Transform 
				position.x="0"
				position.y="12" 
				>
			</Transform>
		</InheritTransformComponent>
		
		<LoadEntitiesComponent
			count.min="0"
			count.max="1"
			kill_entity="0"
			entity_file="data/entities/props/physics_stone_02.xml"
			>
		</LoadEntitiesComponent>
	</Entity>
	
	<!-- ... (other stone entities with varying positions and stone types) ... -->
	
	<!-- Lifetime component for the entire pile -->
	<LifetimeComponent
		lifetime="10"
		>
	</LifetimeComponent>
</Entity>
```

## Modding Considerations

*   **Customization**: You can change the `entity_file` to load different types of props or even custom entities to create unique piles.
*   **Placement**: Adjust `position.x` and `position.y` within the `Transform` components to alter the arrangement of the stones.
*   **Lifetime**: Modify the `lifetime` value to control how long the stone pile persists in the game world.
*   **Variety**: Add more `Entity` blocks with different `LoadEntitiesComponent` and `Transform` settings to increase the complexity and visual appeal of the pile.
*   **Naming**: Rename the root `Entity`'s `name` attribute to something more descriptive for better organization in your mod.