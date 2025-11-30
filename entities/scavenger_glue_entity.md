---
title: Scavenger Glue Entity
category: guides
---

<Entity >
  <Base file="data/entities/animals/scavenger_glue.xml"  include_children="1">
    <DamageModelComponent 
      hp="6.5"
      max_hp="6.5"
	  minimum_knockback_force="100000"
     ></DamageModelComponent >
  </Base>
</Entity>
```

---
title: Scavenger Glue Entity
category: entities
---

# Scavenger Glue Entity

This document describes the `scavenger_glue.xml` entity, which defines a specific type of enemy in Noita.

## Key Attributes

### Base Entity

*   **`file`**: Specifies the base entity file being extended. In this case, it's `data/entities/animals/scavenger_glue.xml`.
*   **`include_children`**: Set to `1`, indicating that child entities defined within this file should also be included.

### DamageModelComponent

This component governs the health and damage-related properties of the entity.

*   **`hp`**: The current health points of the entity. Set to `6.5`.
*   **`max_hp`**: The maximum health points the entity can have. Set to `6.5`.
*   **`minimum_knockback_force`**: The minimum force required to cause knockback. Set to `100000`, suggesting it's quite resistant to being pushed around.