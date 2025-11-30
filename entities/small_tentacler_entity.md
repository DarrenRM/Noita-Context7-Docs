---
title: Small Tentacler Entity
category: entities
---

---

# Small Tentacler Entity

This document describes the `tentacler_small.xml` entity, representing a small tentacler creature in Noita.

## Base Entity

The `tentacler_small.xml` inherits its base properties from `data/entities/animals/tentacler_small.xml`.

## Damage Component

This component defines the health and knockback resistance of the small tentacler.

### Key Attributes:

*   **hp**: The current health points of the entity.
*   **max_hp**: The maximum health points the entity can have.
*   **minimum_knockback_force**: The minimum force required to knock back this entity. A high value indicates significant resistance to knockback.

```xml
<DamageModelComponent
  hp="4.5"
  max_hp="4.5"
  minimum_knockback_force="100000"
></DamageModelComponent>
```

## Tentacle Attachment

The small tentacler entity includes an attached tentacle segment.

### Key Attributes:

*   **file**: Specifies the XML file for the tentacle segment.
*   **Transform**: Defines the position of the tentacle relative to the main entity.

```xml
<Entity>
  <Base file="data/entities/verlet_chains/smalltentacle/tentacler_tentacle_02.xml">
    <InheritTransformComponent>
      <Transform position.x="0" position.y="-8"></Transform>
    </InheritTransformComponent>
  </Base>
</Entity>
```