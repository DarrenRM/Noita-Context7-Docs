---
title: Scavenger Clusterbomb Entity
category: entities
---

# Scavenger Clusterbomb Entity

This document describes the `scavenger_clusterbomb.xml` entity, a type of scavenger that deploys cluster bombs.

## Entity Structure

The entity is based on a core `Base` component, which includes a `DamageModelComponent`.

### Base Component

*   **`file`**: `data/entities/animals/scavenger_clusterbomb.xml` - Specifies the base XML file for this entity.
*   **`include_children`**: `1` - Indicates that child entities should be included.

### DamageModelComponent

This component defines the health of the scavenger.

*   **`hp`**: `12` - The current health points of the entity.
*   **`max_hp`**: `12` - The maximum health points the entity can have.