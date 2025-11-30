---
title: Scavenger SMG Entity
category: entities
---

# Scavenger SMG Entity

This document describes the `scavenger_smg.xml` entity, which represents a Scavenger enemy equipped with an SMG in Noita.

## Key Attributes

*   **`hp`**: The current health of the entity.
*   **`max_hp`**: The maximum health of the entity.

## Base Entity

The entity inherits properties from `data/entities/animals/scavenger_smg.xml` and includes its children.

```xml
<Entity >
  <Base file="data/entities/animals/scavenger_smg.xml"  include_children="1">
    <DamageModelComponent 
      hp="1"
      max_hp="1"
     ></DamageModelComponent >
  </Base>
</Entity>
```