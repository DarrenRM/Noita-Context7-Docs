---
title: Skycrystal Physics Entity
category: entities
---

# Skycrystal Physics Entity

This document describes the `skycrystal_physics.xml` entity, which defines the core physics and damage properties for a skycrystal in Noita.

## Entity Definition

The entity is based on a common `Base` file, indicating it inherits general properties from a template.

```xml
<Entity >
  <Base file="data/entities/animals/skycrystal_physics.xml">
    </Base>
</Entity>
```

## Key Components

### DamageModelComponent

This component governs the health and resilience of the skycrystal.

| Attribute             | Description                                     |
| :-------------------- | :---------------------------------------------- |
| `hp`                  | Current health points of the skycrystal.        |
| `max_hp`              | Maximum health points of the skycrystal.        |
| `minimum_knockback_force` | The minimum force required to cause knockback. |

**Example:**

```xml
    <DamageModelComponent 
      hp="60"
      max_hp="60"
	  minimum_knockback_force="100000"
     ></DamageModelComponent >
```