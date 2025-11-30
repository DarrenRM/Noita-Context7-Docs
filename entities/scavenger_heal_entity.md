---
title: Scavenger Heal Entity
category: guides
---

<Entity>
  <Base file="data/entities/animals/scavenger_heal.xml" include_children="1">
    <DamageModelComponent hp="2" max_hp="2"/>
  </Base>
</Entity>
```

---
title: Scavenger Heal Entity
category: entities
---

# Scavenger Heal Entity

This entity defines a "Scavenger Heal" variant, likely a creature or object that can heal other entities.

## Key Components

### Base Entity
*   **file**: `data/entities/animals/scavenger_heal.xml` - Inherits properties from a base scavenger heal entity.
*   **include_children**: `1` - Indicates that child entities should also be included.

### DamageModelComponent
*   **hp**: `2` - The current health points of the entity.
*   **max_hp**: `2` - The maximum health points the entity can have.

This is a very simple entity, primarily defining the health of a scavenger that can heal. Further functionality would likely be defined in other components or scripts not present in this snippet.