---
title: Fly Entity
category: entities
---

---

# Fly Entity

This document describes the `fly.xml` entity, a common flying creature found in the rainforest biome.

## Base Entity

The fly inherits its base properties from `data/entities/animals/fly.xml`.

## Damage Component

### Key Attributes:

*   **hp**: The current health points of the fly.
*   **max_hp**: The maximum health points the fly can have.

```xml
<Entity>
  <Base file="data/entities/animals/fly.xml">
    <DamageModelComponent
      hp="3"
      max_hp="3">
    </DamageModelComponent>
  </Base>
</Entity>