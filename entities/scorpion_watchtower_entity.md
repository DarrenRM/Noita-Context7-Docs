---
title: Scorpion Watchtower Entity
category: entities
---

---

# Scorpion Watchtower Entity

This document describes the `scorpion_watchtower.xml` entity, a variant of the standard scorpion in Noita, designed for AI-assisted modding.

## Entity Definition

The `scorpion_watchtower.xml` entity is a specialized version of the base `scorpion.xml` entity.

```xml
<Entity tags="mortal,prey" name="$animal_scorpion">
  
	<Base file="data/entities/animals/scorpion.xml" >
	    <CameraBoundComponent
	        max_count="30"
	    ></CameraBoundComponent>
	</Base>

</Entity>
```

## Key Attributes

*   **`name`**: `$animal_scorpion` - Identifies this entity as a scorpion.
*   **`tags`**: `mortal`, `prey` - Indicates the entity can be killed and is a potential target for predators.
*   **`Base`**:
    *   **`file`**: `data/entities/animals/scorpion.xml` - This is the core of the entity, inheriting all properties from the base scorpion.
    *   **`CameraBoundComponent`**:
        *   **`max_count`**: `30` - Limits the maximum number of these entities that can be active within the camera's view. This is a crucial performance optimization.

## Inheritance and Customization

This entity primarily inherits its behavior and appearance from `data/entities/animals/scorpion.xml`. The only explicit customization in this file is the `CameraBoundComponent` with a `max_count` of 30, suggesting a controlled density for this specific type of scorpion.

## Modding Implications

*   **Behavior**: To alter the behavior of the Scorpion Watchtower, you would typically need to modify the base `scorpion.xml` or create a new entity that inherits from it and adds/overrides specific components.
*   **Appearance**: Visual changes would also be managed within the base `scorpion.xml` or through associated sprite/animation files.
*   **Performance**: The `max_count` attribute is a direct lever for controlling how many of these entities can exist simultaneously, impacting game performance.