---
title: Bloom Animal Entity
category: entities
---

# Bloom Animal Entity

This document describes the `bloom.xml` entity, which defines a "Bloom" creature in Noita.

## Key Attributes

### DamageModelComponent
This component governs the creature's health and damage resistance.

| Attribute | Description |
|---|---|
| `hp` | Current health points. |
| `max_hp` | Maximum health points. |

## Entity Structure

The `bloom.xml` entity inherits its base properties from `data/entities/animals/bloom.xml`. The primary modification within this specific file is the definition of its `DamageModelComponent`.

```xml
<Entity >
  <Base file="data/entities/animals/bloom.xml">
    <DamageModelComponent 
      hp="8"
      max_hp="8"
     ></DamageModelComponent >
  </Base>
</Entity>
```