---
title: Scavenger Leader Entity
category: entities
---

# Scavenger Leader Entity

This document describes the `scavenger_leader.xml` entity, a variant of the standard scavenger with enhanced durability.

## Key Attributes

### Base Entity

*   **`file`**: `data/entities/animals/scavenger_leader.xml` - Specifies the base file for this entity.
*   **`include_children`**: `1` - Indicates that child entities and their properties should be included.

### Damage Component

*   **`hp`**: `12` - The current health points of the scavenger leader.
*   **`max_hp`**: `12` - The maximum health points the scavenger leader can have.

This entity inherits its core behavior from `data/entities/animals/scavenger.xml` and primarily modifies its health pool.