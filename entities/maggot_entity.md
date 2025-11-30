---
title: Maggot Entity
category: entities
---

# Maggot Entity

This document describes the `maggot.xml` entity, a basic enemy type in Noita.

## Core Attributes

*   **`hp`**: The current health of the maggot.
*   **`max_hp`**: The maximum health of the maggot.
*   **`minimum_knockback_force`**: A high value indicating that the maggot is very resistant to being knocked back by attacks.

## Base Entity

The maggot inherits its core properties from `data/entities/animals/maggot.xml`. This implies that its fundamental behaviors, animations, and other base characteristics are defined in that parent file.

```xml
<Entity >
  <Base file="data/entities/animals/maggot.xml">
    <DamageModelComponent 
      hp="8.5"
      max_hp="8.5"
	  minimum_knockback_force="100000"
     ></DamageModelComponent >
  </Base>
</Entity>
```