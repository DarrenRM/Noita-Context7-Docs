---
title: Scavenger (Poison) Entity
category: guides
---

<Entity name="$animal_scavenger_poison" >
  	<Base file="data/entities/animals/scavenger_poison.xml" include_children="1" />
	<Entity>
  		<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />
  	</Entity>
</Entity>
```

---
title: Scavenger (Poison) Entity
category: entities
---

# Scavenger (Poison) Entity

This entity defines a poisoned variant of the Scavenger creature in Noita. It inherits its base behavior from `scavenger_poison.xml` and applies a permanent "drunk" effect.

## Key Attributes

*   **`name`**: `$animal_scavenger_poison` - The internal identifier for this entity.
*   **`Base file="data/entities/animals/scavenger_poison.xml" include_children="1"`**: This is the primary inheritance. It means this entity is a Scavenger with poison properties, and all its children (if any) are included.
*   **`Entity`**: This nested entity is responsible for applying the status effect.
    *   **`Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1"`**: This applies a permanent drunk effect to the Scavenger.

## Summary

The `scavenger_poison.xml` entity is a straightforward modification of a base Scavenger. Its primary function is to inherit the Scavenger's AI and behavior while also applying a persistent "drunk" status effect, likely altering its movement or attack patterns.