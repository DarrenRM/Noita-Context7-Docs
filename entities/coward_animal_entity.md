---
title: Coward Animal Entity
category: entities
---

# Coward Animal Entity

This document describes the `coward.xml` entity, which defines a basic animal enemy in Noita.

## Key Attributes

The `coward.xml` entity inherits from `data/entities/animals/coward.xml` and modifies specific components.

### Base Entity

*   **`file`**: `data/entities/animals/coward.xml` - This indicates the base entity definition being extended.

### DamageModelComponent

This component defines the combat properties of the coward.

*   **`hp`**: `10` - The current health points of the entity.
*   **`max_hp`**: `10` - The maximum health points the entity can have.
*   **`minimum_knockback_force`**: `100000` - A very high value, suggesting this entity is resistant to being knocked back by attacks.

### Additional Entity

*   **`Base file="data/entities/misc/animal_energy_shield.xml"`**: This indicates that the coward entity also possesses an energy shield, likely providing defensive capabilities.