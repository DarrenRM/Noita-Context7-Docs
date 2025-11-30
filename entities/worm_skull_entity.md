---
title: Worm Skull Entity
category: entities
---

# Worm Skull Entity

This document describes the `worm_skull.xml` entity, a component of the worm creature in Noita.

## Key Attributes

### DamageModelComponent

This component defines the health and damage properties of the worm skull.

| Attribute | Value | Description |
|---|---|---|
| `hp` | 250 | The current health points of the worm skull. |
| `max_hp` | 250 | The maximum health points the worm skull can have. |

## XML Structure

```xml
<Entity >
  <Base file="data/entities/animals/worm_skull.xml">
    <DamageModelComponent 
      hp="250"
      max_hp="250"
     ></DamageModelComponent >
  </Base>
</Entity>
```