---
title: Necromancer Entity
category: entities
---

# Necromancer Entity

This document describes the `necromancer.xml` entity, a hostile creature found in the crypt.

## Key Attributes

### Base Entity

*   **File:** `data/entities/animals/necromancer.xml`
    *   This indicates the Necromancer inherits properties from a base `necromancer.xml` file, likely defining its core behaviors and appearance.

### Damage Component

*   **HP:** `17`
    *   The current health points of the Necromancer.
*   **Max HP:** `17`
    *   The maximum health points the Necromancer can have.
*   **Minimum Knockback Force:** `100000`
    *   A very high value, suggesting the Necromancer is resistant to being knocked back by attacks.

```xml
<Entity >
  <Base file="data/entities/animals/necromancer.xml">
    <DamageModelComponent 
      hp="17"
      max_hp="17"
	  minimum_knockback_force="100000"
     ></DamageModelComponent >
  </Base>
</Entity>
```