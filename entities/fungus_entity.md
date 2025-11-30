---
title: Fungus Entity
category: entities
---

# Fungus Entity

This document describes the `fungus.xml` entity, a basic fungal creature found in the rainforest biome.

## Core Attributes

*   **`hp`**: The current health points of the fungus.
*   **`max_hp`**: The maximum health points the fungus can have.

## XML Structure

```xml
<Entity >
  <Base file="data/entities/animals/fungus.xml">
    <DamageModelComponent 
      hp="5.2"
      max_hp="5.2"
     ></DamageModelComponent >
  </Base>
</Entity>
```