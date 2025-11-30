---
title: Scavenger Heal Entity (Drunk Variant)
category: guides
---

<Entity name="$animal_scavenger_heal">
  <Base file="data/entities/animals/scavenger_heal.xml" include_children="1"/>
  <Entity>
    <Base file="data/entities/misc/effect_drunk_forever.xml" include_children="1"/>
  </Entity>
</Entity>
```

---
title: Scavenger Heal Entity (Drunk Variant)
category: entities
---

# Scavenger Heal Entity (Drunk Variant)

This entity defines a drunk variant of the Scavenger creature in Noita, which has a unique healing behavior.

## Key Attributes

*   **`name`**: `$animal_scavenger_heal` - The internal identifier for this entity.
*   **`Base file="data/entities/animals/scavenger_heal.xml"`**: Inherits core properties and behaviors from the standard `scavenger_heal.xml` entity. This means it shares the fundamental characteristics of a healing scavenger.
*   **`Entity`**: This nested entity introduces additional effects or modifications.
    *   **`Base file="data/entities/misc/effect_drunk_forever.xml"`**: This is the crucial element that makes this variant "drunk." It applies a permanent drunk effect to the scavenger, likely influencing its movement, AI, or other behaviors.

## Summary

The `$animal_scavenger_heal` entity is a specialized version of the Scavenger creature. It inherits the healing capabilities of its base entity but is further modified by the `effect_drunk_forever.xml` to exhibit behaviors associated with being permanently drunk. This likely results in a less predictable or more erratic version of the healing scavenger.