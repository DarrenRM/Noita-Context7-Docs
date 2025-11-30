---
title: Scavenger Grenade Entity
category: guides
---

<Entity name="$animal_scavenger_grenade" >
  	<Base file="data/entities/animals/scavenger_grenade.xml" include_children="1" />
	<Entity>
  		<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />
  	</Entity>
 </Entity>
```

---
title: Scavenger Grenade Entity
category: entities
---

# Scavenger Grenade Entity

This document describes the `scavenger_grenade.xml` entity, which represents a specific type of enemy in Noita.

## Key Attributes

*   **`name`**: `$animal_scavenger_grenade` - The internal identifier for this entity.
*   **`Base`**:
    *   `file="data/entities/animals/scavenger_grenade.xml"`: Inherits core properties from the base `scavenger_grenade.xml` entity.
    *   `include_children="1"`: Ensures that all child elements from the base file are included.

## Inherited Effects

This entity also incorporates effects from other base files:

*   **`Entity`**:
    *   **`Base`**:
        *   `file="data/entities/misc/effect_drunk_forever.xml"`: Applies a permanent "drunk" effect to the entity.
        *   `include_children="1"`: Includes all child elements from the `effect_drunk_forever.xml` file.