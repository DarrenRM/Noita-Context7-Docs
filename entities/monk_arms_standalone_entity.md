---
title: Monk Arms Standalone Entity
category: entities
---

---

# Monk Arms Standalone Entity

This entity defines a standalone configuration for monk arms, likely for use in custom scenarios or as a building block for other entities. It primarily inherits and configures existing `monk_arm.xml` and `monk_arm_fx.xml` entities.

## Key Components and Inheritance

The core functionality is derived from other entity definitions.

### `monk_arm.xml` Inheritance

The entity reuses the `monk_arm.xml` definition multiple times, allowing for variations.

*   **Base `monk_arm.xml`:** This is the fundamental definition for a monk arm.
*   **Flipped Arm:** One instance of `monk_arm.xml` includes a `SpriteComponent` with `special_scale_x="-1"`. This flips the arm horizontally, creating a mirrored version.
*   **Variable Storage:** The flipped arm also includes a `VariableStorageComponent` with `value_bool="0"`. The purpose of this specific boolean variable is not detailed in this snippet but suggests a configurable state.

### `monk_arm_fx.xml` Inheritance

Each instance of the monk arm is augmented with visual effects defined in `monk_arm_fx.xml`.

*   **`arm_fx` Tag:** Entities inheriting from `monk_arm_fx.xml` are tagged with `arm_fx`. This likely groups them for specific game logic or rendering.

## Structure

The entity is structured hierarchically:

```xml
<Entity>
	<InheritTransformComponent /> <!-- Inherits transform properties -->
	<Entity> <!-- First set of monk arms -->
		<Base file="data/entities/misc/monk_arm.xml">
		</Base>
		<!-- Three instances of monk_arm_fx.xml -->
		<Entity tags="arm_fx">
			<Base file="data/entities/misc/monk_arm_fx.xml" />
		</Entity>
		<Entity tags="arm_fx">
			<Base file="data/entities/misc/monk_arm_fx.xml" />
		</Entity>
		<Entity tags="arm_fx">
			<Base file="data/entities/misc/monk_arm_fx.xml" />
		</Entity>
	</Entity>
	<Entity> <!-- Second set of monk arms (flipped) -->
		<Base file="data/entities/misc/monk_arm.xml">
			<SpriteComponent
				has_special_scale="1"
				special_scale_x="-1" >
			</SpriteComponent>
			<VariableStorageComponent
				value_bool="0">
			</VariableStorageComponent>
		</Base>
		<!-- Three instances of monk_arm_fx.xml -->
		<Entity tags="arm_fx">
			<Base file="data/entities/misc/monk_arm_fx.xml" />
		</Entity>
		<Entity tags="arm_fx">
			<Base file="data/entities/misc/monk_arm_fx.xml" />
		</Entity>
		<Entity tags="arm_fx">
			<Base file="data/entities/misc/monk_arm_fx.xml" />
		</Entity>
	</Entity>
</Entity>
```

## AI Modding Considerations

*   **Reusability:** This entity serves as a template for creating multiple monk arms with specific orientations and potential states.
*   **Inheritance:** Understanding the base entities (`monk_arm.xml`, `monk_arm_fx.xml`) is crucial for modifying or extending this configuration.
*   **Component Overrides:** The `SpriteComponent` and `VariableStorageComponent` demonstrate how to override or add specific properties to inherited base entities.
*   **Tagging:** The `arm_fx` tag is important for identifying and potentially manipulating these effect entities.