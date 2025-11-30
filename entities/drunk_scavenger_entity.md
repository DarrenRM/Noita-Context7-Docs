---
title: Drunk Scavenger Entity
category: entities
---

# Drunk Scavenger Entity

This document describes the `scavenger_invis.xml` entity, which represents a "drunk" variant of the Scavenger enemy in Noita.

## Entity Definition

The core of this entity is defined by its `name` attribute.

```xml
<Entity name="$animal_scavenger_invis" >
```

## Inheritance and Effects

This entity inherits its base properties from another Scavenger entity and applies a permanent drunk effect.

### Base Entity

The `Base` tag indicates that this entity inherits from `data/entities/animals/scavenger_invis.xml`. The `include_children="1"` attribute ensures that all child elements from the base file are also included.

```xml
	<Base file="data/entities/animals/scavenger_invis.xml" include_children="1" />
```

### Drunk Effect

An additional `Entity` block is used to apply a specific effect.

```xml
	<Entity>
  		<Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1" />
  	</Entity>
```

This nested `Base` tag points to `data/entities/misc/effect_drunk_forever.xml`, which applies a permanent drunk status to the entity.