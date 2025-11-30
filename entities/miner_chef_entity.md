---
title: Miner Chef Entity
category: entities
---

# Miner Chef Entity

This document describes the `miner_chef.xml` entity, which represents a "Miner Chef" creature in Noita.

## Entity Definition

The `miner_chef.xml` entity is defined as follows:

```xml
<Entity name="$animal_cook" >
 	<Base file="data/entities/animals/miner_chef.xml" include_children="1" />
	<Entity>
  		<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />
  	</Entity>
 </Entity>
```

### Key Components:

*   **`name="$animal_cook"`**: This is the internal name for the entity, likely used for referencing in game logic and scripts.
*   **`<Base file="data/entities/animals/miner_chef.xml" include_children="1" />`**: This indicates that the entity inherits properties and definitions from its own base file, `miner_chef.xml`. `include_children="1"` suggests that any child elements within this base file are also incorporated.
*   **`<Entity><Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" /></Entity>`**: This nested entity applies the `effect_drunk_forever.xml` effect to the Miner Chef. This means the creature will perpetually be under the influence of a "drunk" status effect.

## Functionality and Behavior

The primary characteristic of the Miner Chef, as indicated by its XML definition, is its permanent "drunk" state. This likely influences its movement patterns, AI, and potentially its combat behavior or interactions with the environment.

### Inherited Behavior

The entity inherits its core AI and physical properties from `data/entities/animals/miner_chef.xml`. Without access to that specific file, detailed behavioral attributes cannot be listed here. However, it can be inferred that it possesses typical animal-like behaviors, potentially related to mining or cooking, modified by its intoxicated state.

### Drunk Effect

The inclusion of `effect_drunk_forever.xml` is a significant modifier. This effect typically causes:

*   Unpredictable movement.
*   Potentially altered attack patterns or accuracy.
*   Visual distortions or other status effects associated with being drunk in Noita.

## AI Modding Considerations

When modding the Miner Chef, consider the following:

*   **Base AI Modification**: If you wish to alter its fundamental behaviors (e.g., making it more aggressive, passive, or changing its target priorities), you would need to modify the original `miner_chef.xml` file or create a new entity that overrides its AI components.
*   **Drunk Effect Customization**: While the `effect_drunk_forever.xml` is applied, its specific parameters might be configurable within that file or through game settings. Modifying this effect could change the intensity or nature of the "drunk" status.
*   **Interaction with Other Entities**: The "drunk" state might affect how the Miner Chef interacts with other creatures or environmental elements.

This entity serves as a good example of how to combine base creature definitions with specific status effects to create unique variations of existing in-game entities.