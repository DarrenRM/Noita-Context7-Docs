---
title: Drunk Miner Entity
category: guides
---

<Entity name="$animal_miner_fire" >
  	<Base file="data/entities/animals/miner_fire.xml" include_children="1" />
	<Entity>
  		<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />
  	</Entity>
</Entity>
```

---
title: Drunk Miner Entity
category: entities
---

# Drunk Miner Entity

This document describes the configuration for the "Drunk Miner" entity in Noita, primarily focusing on its integration and inherited properties.

## Entity Definition

The core of this entity is defined by its name and inheritance from a base file.

### Key Attributes

*   **`name`**: `$animal_miner_fire` - This is the internal identifier for the entity.
*   **`Base`**:
    *   `file`: `data/entities/animals/miner_fire.xml` - This indicates that the entity inherits all properties and definitions from the `miner_fire.xml` file located in the `data/entities/animals/` directory.
    *   `include_children`: `1` - This ensures that all child elements defined within `miner_fire.xml` are also included in this entity.

## Inherited Effects

This entity also incorporates a specific effect through an additional `Entity` block.

### Key Attributes

*   **`Entity`**:
    *   **`Base`**:
        *   `file`: `data/entities/misc/effect_drunk_forever.xml` - This signifies that the entity inherits the "drunk forever" effect from the specified file in the `data/entities/misc/` directory.
        *   `include_children`: `1` - All child elements from `effect_drunk_forever.xml` are included.

## Summary

The `$animal_miner_fire` entity is essentially a "miner" entity that is permanently under the influence of alcohol, as defined by the `effect_drunk_forever.xml` file. Its primary behavior and appearance are derived from `data/entities/animals/miner_fire.xml`.